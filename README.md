# Pytorch deployment with Flask

Deplying an image classifier with pytorch and Flask

`pip install -r requirements.txt`

Set up API

`python src/flask_api.py --model_path model/model_checkpoint.pth --class_index_path model/class_index_dict.json --endpoint_name classifier --host localhost --port 5000`

Make predictions

`python src/predict.py --img_dir test_images --XAI False --endpoint_name classifier --host localhost --port 5000`

The model can be trained using the repo: https://github.com/europeana/rd-img-classification-pilot

# Run with docker

pull the image

`docker pull axiom1123/torch_deployment:v4`

as soon as you downloaded the image execute the command

`docker run -t -p 0.0.0.0:3030:3030 
        torch_deployment:v4 
        python src/flask_api.py --model_path model/model_checkpoint.pth --class_index_path model/class_index_dict.json --endpoint_name classifier --host 0.0.0.0 --port 3030`

the container is running now and the service is available

# Run with Startup script

simple run the bash-script 

`bash start.sh`
