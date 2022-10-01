# Awair-Home-Coding-Assignment


#### 1
```
docker-compose up -d
```
Deploying rabbitMQ and PostgreSQL

#### 2
Going to RabbitMQ admin dashboard and need create queue with name "devices"
guest/guest

```
    http://localhost:15672/#/queues
```

#### 3
Need create new table on PostgreSQL
```
-- Table: public.devices

-- DROP TABLE IF EXISTS public.devices;

CREATE TABLE IF NOT EXISTS public.devices
(
    id integer NOT NULL DEFAULT nextval('devices_id_seq'::regclass),
    device_id character(50) COLLATE pg_catalog."default",
    type character(50) COLLATE pg_catalog."default",
    latitude double precision,
    longitude double precision,
    status character(50) COLLATE pg_catalog."default",
    timezone character(50) COLLATE pg_catalog."default",
    created_at timestamp without time zone NOT NULL DEFAULT CURRENT_TIMESTAMP,
    CONSTRAINT devices_pkey PRIMARY KEY (id),
    CONSTRAINT uniq UNIQUE (device_id)
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.devices
    OWNER to postgres;
    
```

#### 4 
Run Client and Device services

##### DeviceService
```
    https://github.com/teka808/deviceService
```


##### ClientService
```
    https://github.com/teka808/clientService
```