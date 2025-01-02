# SdiffusionUE  

### 🚀 Bring AI-Powered Image Generation to Unreal Engine!  

**SdiffusionUE** is a powerful Unreal Engine plugin that integrates with **Stable Diffusion**, allowing you to generate stunning AI-generated images directly within your Unreal Engine projects. Whether you're creating high-quality textures, concept art, or unique visuals, this plugin is your gateway to endless creativity!  

---

## 🎨 Features  

- **Custom Prompts**: Generate images based on your specific descriptions.  
- **Advanced Settings**: Fine-tune image properties like resolution, steps, sampler, and more.  
- **High-Resolution Mode**: Enable high-res generation with configurable upscaling and second-pass enhancements.  
- **Seamless Integration**: Outputs generated images as `UTexture2D` assets for immediate use in your project.  
- **Real-Time Feedback**: Receive status updates using dynamic multicast delegates.  
- **Extensible**: Built with Unreal's HTTP and JSON utilities for easy customization.  

---

## 🛠️ Installation  

1. Clone or download the **SdiffusionUE** plugin to your Unreal Engine project:  
   ```bash
   git clone https://github.com/your-repo/SdiffusionUE.git
   ```  
2. Place the plugin in your project’s `Plugins` folder:  
   ```
   YourProject/
   ├── Plugins/
       ├── SdiffusionUE/
   ```  
3. Open your project in Unreal Engine and enable the plugin in **Edit > Plugins**.  
4. Restart your project to complete the setup.  

---

## 🧑‍💻 Usage  

1. Start your Stable Diffusion API server locally (ensure it’s accessible on `http://127.0.0.1:port`).  
2. In Unreal Engine, call `SetRequestAddress` with the correct port to configure the API endpoint.  
3. Use `GenerateImage` to send a payload with your desired parameters:  
   ```cpp
   FSDiffusionPayload Payload;
   Payload.Prompt = "A futuristic cityscape at sunset";
   Payload.Width = 1024;
   Payload.Height = 1024;
   Payload.Steps = 75;
   USdiffusionUFunctionLibrary::GenerateImage("http://127.0.0.1:7860/sdapi/v1/txt2img", Payload);
   ```  
4. Listen for the `OnImageGenerated` delegate to retrieve the generated image's path and status.  
5. Optionally, use `DecodeImage` to load the generated image as a `UTexture2D` for use in your project.  

---

## 📦 Example Blueprint  

You can also use **SdiffusionUE** in Blueprints! Here's how:  
- Call `SetRequestAddress` to set the API URL.  
- Use the `GenerateImage` node to send the payload.  
- Bind to the `OnImageGenerated` delegate to handle the results.  

---

## 🔧 Configuration  

The following parameters can be configured in the payload:  

| Parameter         | Description                         | Default Value  |  
|-------------------|-------------------------------------|----------------|  
| **Prompt**        | Description of the image to create | `"A sunset"`   |  
| **NegativePrompt**| What to avoid in the image         | `""`           |  
| **Width**         | Width of the image                 | `512`          |  
| **Height**        | Height of the image                | `512`          |  
| **Steps**         | Number of sampling steps           | `50`           |  
| **CfgScale**      | Guidance scale                     | `7.0`          |  
| **HrScale**       | Upscaling factor for high-res mode | `2.0`          |  

---

## 🧑‍🎨 Made By  

**Ow1onp**  
Your creative companion for Unreal Engine projects!  

---

## 📜 License  

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and contribute to this plugin.  

---

### 🌟 Unleash your creativity with **SdiffusionUE**!
