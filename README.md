# Xbox Game Bar Modern Sample

This sample is based on [microsoft/XboxGameBarSamples: Samples/WidgetSampleCS](https://github.com/microsoft/XboxGameBarSamples/tree/master/Samples/WidgetSampleCS), but modernized to use .NET 9.

## Follow by Steps

0. Create a new .NET 9 UWP project in Visual Studio, and follow [official guide](https://learn.microsoft.com/en-us/gaming/game-bar/) to set up the project, but **DO NOT** add the SDK NuGet reference.
1. Install [CsWinRT](https://github.com/microsoft/CsWinRT) in NuGet package manager.
2. Extact `Microsoft.Gaming.XboxGameBar.winmd` from [Xbox Game Bar SDK](https://www.nuget.org/packages/Microsoft.Gaming.XboxGameBar) and add it as a reference in your project.
3. Add following to your .csproj file:

    ```xml
    <Project>
      <!-- ... -->
      <PropertyGroup>
        <CsWinRTIncludes>Microsoft.Gaming.XboxGameBar</CsWinRTIncludes>
      </PropertyGroup>
    </Project>
    ```

## License

This project is licensed samely as the original sample (MIT License), see also: [Code of Conduct](https://github.com/microsoft/XboxGameBarSamples?tab=coc-ov-file#readme).
