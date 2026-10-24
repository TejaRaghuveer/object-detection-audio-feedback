# Object detection with audio feedback

A small Colab notebook. You upload a photo, a pretrained YOLO model (`yolo11n`) finds the objects in it, the notebook draws a box and label around each one, and then reads out a short summary like "Detected 5 persons, 1 sports ball." using Google text-to-speech.

I made it as a first project with object detection, and the idea was to have the result spoken as well as shown.

## Run it

1. Open `object_detection_audio_feedback.ipynb` in Google Colab (File > Upload notebook).
2. Run the cells from the top. The first one installs `ultralytics` and `gTTS`.
3. When asked, upload an image. You get the annotated image, the text summary and an audio player.

It uses `google.colab.files.upload`, so it runs in Colab as written. To run locally, replace the upload step with a file path.

## Notes

- The model is the pretrained `yolo11n.pt` from Ultralytics. There is no training and I have not measured accuracy.
- Detection uses the default confidence threshold. Small or partly hidden objects can be missed.
- gTTS needs an internet connection.
- No sample image is included. Use your own photo.

## Ideas for next steps

- Run on a webcam or video instead of one image
- Say where each object is (left, centre, right) as well as what it is
- Let the user set the confidence threshold
