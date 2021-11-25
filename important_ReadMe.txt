-predict
python predict.py --image ./Segmentation/images/valid/9908_Acanthopagrus_palmaris_f000020.jpg --mask ./Segmentation/masks/valid/9908_Acanthopagrus_palmaris_f000020.png --save_to ./outputs/predict.jpg --experiment_name "marine"

-runner

python runner.py --train_path ./Segmentation/images --mask_path ./Segmentation/masks --experiment_name "experiment_name"

wiederholte training
python runner.py --train_path ./Segmentation/images --mask_path ./Segmentation/masks --experiment_name "experiment_name" -from_weights

Pipeline outcomes
During the training procedure the pipeline logs additional results to the outputs directory:

# Clear any logs from previous runs
rm -rf ./logs/

outputs/experiment_name/logs contains TensorBoard logs
outputs/experiment_name/predicted_pics/warm_up_generator contains the model predictions for the specific steps in the warm up generator training mode
outputs/experiment_name/predicted_pics/wgan contains the model predictions for the specific steps in the WGAN-GP training mode
outputs/experiment_name/weights contains the generator and critics models weights
outputs/experiment_name/summaries contains the generator