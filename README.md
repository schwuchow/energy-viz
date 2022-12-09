# How to get the project running

Clone the repository. The project uses the SpeechRecognizer from the Speech SDK. It uses an example from https://github.com/Azure-Samples/cognitive-services-speech-sdk/tree/master/samples/csharp/unity/from-unitymicrophone.

The project currently contains two asssets/packages: The Speech SDK as well as the 2D Sprites package.

To use the SpeechRecognizer, it is necessary to have a running Cognitive Speech Service running in Azure from which the the name and region key need to be extracted. The Cognitive Speech Service is already running and all you have to do is add the keys of the service to your local project.
In `SpeechRecognition.cs` you will find the following code:

    /*
    Read Speech SDK CognitiveService keys from json file to create a config for the SpeechRecognizer
    */
    string jsonPath = Application.dataPath + "/Scripts/keys.json";
    string jsonStr = File.ReadAllText(jsonPath);
    CognitiveService keys = JsonUtility.FromJson<CognitiveService>(jsonStr);

Create a `key.json` file in the `Scripts` folder with these lines. Replace `KEY` and `REGION` with what was sent to you. 

    {
        "cognitiveServiceKey": "KEY",
        "cognitiveServiceRegion": "REGION"
    }

Then run the application and try it out.

* [Quickstart article on the SDK documentation site](https://docs.microsoft.com/azure/cognitive-services/speech-service/quickstart-csharp-unity)
* [Speech SDK API reference for C#](https://aka.ms/csspeech/csharpref)
