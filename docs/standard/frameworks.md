---
title: Zielframeworks in Projekten im SDK-Format – .NET
description: Erfahren Sie mehr über Zielframeworks für .NET Core-Anwendungen und -Bibliotheken.
ms.date: 12/03/2019
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: c1fd3a6fe07526d9f6828851c591ed0155c79a19
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164297"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Zielframeworks in Projekten im SDK-Format

Wenn Sie ein Framework in einer App oder Bibliothek als Ziel verwenden, geben Sie mehrere APIs an, die Sie für die App oder Bibliothek verfügbar machen möchten. Sie geben das Zielframework mit Zielframeworkmonikers (TFMs) in Ihrer Projektdatei an.

Eine App oder Bibliothek kann eine Version des [.NET Standards](net-standard.md) als Ziel verwenden. .NET Standard-Versionen stellen standardisierte APIs in allen .NET-Implementierungen dar. Eine Bibliothek kann z.B. NET Standard 1.6 als Ziel verwenden und Zugriff auf APIs erhalten, die sowohl in .NET Core und .NET Framework mit der gleichen Codebasis funktionieren.

Eine App oder Bibliothek kann auch eine spezifische .NET-Implementierung als Ziel verwenden, um Zugriff auf implementierungsspezifische APIs zu erhalten. Eine App, die beispielsweise Xamarin.iOS als Ziel verwendet (z.B. `Xamarin.iOS10`), erhält Zugriff auf von Xamarin bereitgestellte API-Wrapper für iOS 10, und eine App, die die universelle Windows-Plattform (UWP, `uap10.0`) als Ziel verwendet, erhält Zugriff auf APIs, die für Geräte kompilieren, die unter Windows 10 ausgeführt werden.

Für einige Zielplattformen (z.B. .NET Framework) werden die APIs von den Assemblys definiert, die das Framework auf einem System installiert, und zu denen möglicherweise Anwendungsframework-APIs zählen (z.B. ASP.NET).

Für paketbasierte Zielframeworks (z.B. .NET Standard und .NET Core) werden die APIs von den Paketen definiert, die in der App oder der Bibliothek enthalten sind. Ein *Metapaket* ist ein NuGet-Paket ohne eigenen Inhalt, das aus einer Liste von Abhängigkeiten oder Paketen besteht. Ein Zielframework, das auf einem NuGet-Paket basiert, gibt implizit ein Metapaket an, das auf alle Pakete verweist, aus denen das Framework besteht.

## <a name="latest-target-framework-versions"></a>Neueste Zielframeworkversionen

Die folgende Tabelle listet die häufigsten Zielframeworks auf, wie auf diese verwiesen wird und welche Version von [.NET Standard](net-standard.md) von ihnen implementiert wird. Diese Zielframeworkversionen sind die neuesten stabilen Versionen. Vorabversionen werden nicht angezeigt. Ein TFM ist ein standardisiertes Tokenformat zum Angeben des Zielframeworks einer .NET-App oder -Bibliothek.

| Zielframework      | Latest <br/> Stabile Version | Zielframeworkmoniker (Target Framework Moniker, TFM) | Implementiert <br/> .NET-Standardversion |
| :-------------------: | :-------------------------: | :----------------------------: | :-------------------------------------: |
| .NET Standard         | 2.1                         | netstandard2.1                 | –                                     |
| .NET Core             | 3.1                         | netcoreapp3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2,0                                     |

## <a name="supported-target-framework-versions"></a>Unterstützte Zielframeworkversionen

Auf ein Zielframework wird normalerweise mit einem TFM verwiesen. In der folgenden Tabelle werden die vom .NET Core SDK und dem NuGet-Client unterstützten Zielframeworks aufgelistet. Äquivalente werden in Klammern angegeben. `win81` ist z.B ein äquivalenter TFM von `netcore451`.

| Zielframework           | TFM |
| -------------------------- | --- |
| .NET Standard              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard2.1 |
| .NET Core                  | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp3.0<br>netcoreapp3.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Windows Store              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| Universelle Windows-Plattform | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

## <a name="how-to-specify-target-frameworks"></a>Angeben von Zielframeworks

Zielframeworks geben Sie in Ihrer Projektdatei an. Wenn ein einzelnes Framework angegeben wird, verwenden Sie das Element **TargetFramework**. Die folgende Projektdatei einer Konsolen-App veranschaulicht, wie Sie .NET Core 3.0 als Ziel verwenden können:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Wenn Sie mehrere Zielframeworks angeben, können Sie bedingt auf Assemblys für jedes Zielframework verweisen. Sie können in Ihrem Code bedingt mit diesen Assemblys kompilieren, indem Sie die Präprozessorsymbole mit *wenn-dann-sonst*-Logik verwenden.

Die folgende Bibliotheksprojektdatei verwendet APIs von .NET Standard (`netstandard1.4`) und von .NET Framework (`net40` und `net45`) als Ziel. Verwenden Sie das Element **TargetFrameworks** im Plural für mehrer Zielframeworks. Beachten Sie, dass die `Condition`-Attribute implementierungsspezifische Pakete enthalten, wenn die Bibliothek für die zwei .NET Framework-TFMs kompiliert wird:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

Sie schreiben in Ihrer Bibliothek oder App bedingten zu kompilierenden Code für jedes Zielframework:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

Das Buildsystem beachtet Präprozessorsymbole, die Zielframeworks darstellen, die in der Tabelle [Unterstützte Zielframeworkversionen](#supported-target-framework-versions) aufgelistet sind, wenn Sie Projekte im SDK-Format verwenden. Wenn Sie ein Symbol verwenden, das einen TFM von .NET Standard oder .NET Core darstellt, ersetzen Sie den Punkt (.) durch einen Unterstrich (_), und ändern Sie Klein- in Großbuchstaben (das Symbol für `netstandard1.4` ist z.B. `NETSTANDARD1_4`).

Hier finden Sie eine vollständige Liste der Präprozessorsymbole für .NET Core-Zielframeworks:

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Veraltete Zielframeworks

Die folgenden Zielframeworks sind veraltet. Pakete, die für diese Zielframeworks ausgelegt sind, sollten zur jeweiligen Ersetzung migriert werden.

| Veralteter TFM                                                                             | Ersetzung |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>dnx<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | uap10.0     |
| win                                                                                        | netcore45   |
| win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | uap10.0     |
| winrt                                                                                      | netcore45   |

## <a name="see-also"></a>Weitere Informationen

- [Entwickeln von Bibliotheken mit plattformübergreifenden Tools](../core/tutorials/libraries.md)
- [.NET-Standard](net-standard.md)
- [.NET Core-Versionskontrolle](../core/versions/index.md)
- [dotnet/standard-GitHub-Repository](https://github.com/dotnet/standard)
- [GitHub-Repository NuGet-Tools)](https://github.com/joelverhagen/NuGetTools)
- [Frameworkprofile in .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
