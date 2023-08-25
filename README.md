# datapipeline-weather-api
ETL process

1. Create EC2 instance (Linux VM, t2.small)
    1.1. set inbound rule 
        1.1.1. customTCP, portrange: 8080, source: Anywhere IPV4
    
2. Create python environment  and install libs in VM
    2.1. sudo apt update -y
    2.2. sudo apt install python3-pip -y
    2.3. sudo apt install python3.10-venv -y
    2.4. python3 -m venv airflow_venv
    2.5. activate venv by this command: source airflow_venv/bin/activate
    2.6. install dependencies
        2.6.1. sudo pip install pandas
        2.6.2. sudo pip install s3sf
        2.6.3. sudo pip install apache-airflow
    2.7. airflow standalone
        2.7.1. recieve user: admin and password: .....

3. Log-in to apache airflow
    3.1 copy address from Public IPV4 DNS (in created EC2 instance) follow by : portrange
        ex. ec2-xx-xx-xxx-xx.us-east-1.compute.amazonaws.com:8080

4. Remote to EC2 via Vscode
    in .ssh folder > config
    
    Host {EC2 name}
        Hostname {public IP}
        User ubuntu # (depends on type of vm)
        IdentifyFile: {key.pem filepath in local}
