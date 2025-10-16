# Xbox Game Bar Modern Sample

This sample is based on [microsoft/XboxGameBarSamples: Samples/WidgetSampleCS](https://github.com/microsoft/XboxGameBarSamples/tree/master/Samples/WidgetSampleCS), but modernized to use .NET 9.

## Follow by Steps

0. Create a new .NET 9 UWP project in Visual Studio, and follow [official guide](https://learn.microsoft.com/en-us/gaming/game-bar/) to set up the project.
1. Install [CsWinRT](https://github.com/microsoft/CsWinRT) in NuGet package manager.
2. Add following to your .csproj file:

    ```xml
    <Project>
        <!-- ... -->
      <PropertyGroup>
        <Native-Platform Condition="'$(Platform)' == 'Win32'">x86</Native-Platform>
        <Native-Platform Condition="'$(Platform)' != 'Win32'">$(Platform)</Native-Platform>
      </PropertyGroup>
      <ItemGroup>
        <ReferenceCopyLocalPaths Include="$(PkgMicrosoft_Gaming_XboxGameBar)\lib\uap10.0\Microsoft.Gaming.XboxGameBar.winmd" />
        <ReferenceCopyLocalPaths Include="$(PkgMicrosoft_Gaming_XboxGameBar)\runtimes\win10-$(Native-Platform)\native\Microsoft.Gaming.XboxGameBar.dll" />
        <ReferenceCopyLocalPaths Include="$(PkgMicrosoft_Gaming_XboxGameBar)\runtimes\win10-$(Native-Platform)\native\Microsoft.Gaming.XboxGameBar.pri" />
        <ReferenceCopyLocalPaths Include="$(PkgMicrosoft_Gaming_XboxGameBar)\private\Microsoft.Gaming.XboxGameBar.Private.winmd" />
        <CsWinRTInputs Include="$(PkgMicrosoft_Gaming_XboxGameBar)\lib\uap10.0\Microsoft.Gaming.XboxGameBar.winmd" />
      </ItemGroup>
      <PropertyGroup>
        <CsWinRTIncludes>
          Microsoft.Gaming.XboxGameBar;
          Microsoft.Gaming.XboxGameBar.Authentication;
          Microsoft.Gaming.XboxGameBar.Input;
        </CsWinRTIncludes>
      </PropertyGroup>
    </Project>
    ```

## License

This project is licensed samely as the original sample (MIT License), see also: [Code of Conduct](https://github.com/microsoft/XboxGameBarSamples?tab=coc-ov-file#readme).
