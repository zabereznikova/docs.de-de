---
title: Zielframeworks in Projekten im SDK-Format – .NET
description: In diesem Artikel erfahren Sie mehr über Zielframeworks für .NET-Anwendungen und -Bibliotheken.
ms.date: 09/08/2020
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 85bc05f07cfcc5f59a8a27790ee3d78a497cecdc
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223456"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Zielframeworks in Projekten im SDK-Format

Wenn Sie ein Framework in einer App oder Bibliothek als Ziel verwenden, geben Sie mehrere APIs an, die Sie für die App oder Bibliothek verfügbar machen möchten. Das Zielframework wird mithilfe von Zielframeworkmonikern (Target Framework Monikers, TFMs) in Ihrer Projektdatei angegeben.

Eine App oder Bibliothek kann eine Version des [.NET Standards](net-standard.md) als Ziel verwenden. .NET Standard-Versionen stellen standardisierte APIs in allen .NET-Implementierungen dar. Eine Bibliothek kann z.B. NET Standard 1.6 als Ziel verwenden und Zugriff auf APIs erhalten, die sowohl in .NET Core und .NET Framework mit der gleichen Codebasis funktionieren.

Eine App oder Bibliothek kann auch eine spezifische .NET-Implementierung als Ziel verwenden, um Zugriff auf implementierungsspezifische APIs zu erhalten. Eine App für Xamarin.iOS (z. B. `Xamarin.iOS10`) kann beispielsweise auf von Xamarin bereitgestellte API-Wrapper für iOS 10 zugreifen, während eine App, die für die universelle Windows-Plattform (UWP, `uap10.0`) entwickelt wurde, Zugriff auf APIs hat, die Code für Windows 10-Geräte kompilieren.

Für einige Zielframeworks (z. B. das .NET Framework) werden die APIs von den Assemblys definiert, die das Framework in einem System installiert. Zu diesen APIs können auch Anwendungsframework-APIs zählen (z. B. ASP.NET).

Für paketbasierte Zielframeworks (z.B. .NET Standard und .NET Core) werden die APIs von den Paketen definiert, die in der App oder der Bibliothek enthalten sind. Ein *Metapaket* ist ein NuGet-Paket ohne eigenen Inhalt, das aus einer Liste von Abhängigkeiten oder Paketen besteht. Ein Zielframework, das auf einem NuGet-Paket basiert, gibt implizit ein Metapaket an, das auf alle Pakete verweist, aus denen das Framework besteht.

## <a name="latest-versions"></a>Neueste Versionen

In der folgenden Tabelle wird aufgelistet, wie die häufigsten Zielframeworks lauten, wie auf diese verwiesen wird und welche Version von [.NET Standard](net-standard.md) sie implementieren. Diese Zielframeworkversionen sind die neuesten stabilen Versionen. Vorabversionen werden nicht angezeigt. Ein TFM ist ein standardisiertes Tokenformat zum Angeben des Zielframeworks einer .NET-App oder -Bibliothek.

| Zielframework      | Latest <br/> Stabile Version | TFM | Implementiert <br/> .NET Standard-Version |
| :-: | :-: | :-: | :-: |
| .NET Standard         | 2.1                         | netstandard2.1                 | –                                     |
| .NET Core             | 3.1                         | netcoreapp3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2,0                                     |

## <a name="supported-target-frameworks"></a>Unterstützte Zielframeworks

Auf ein Zielframework wird normalerweise mit einem TFM verwiesen. In der folgenden Tabelle werden die vom .NET SDK und dem NuGet-Client unterstützten Zielframeworks aufgelistet. Äquivalente werden in Klammern angegeben. `win81` ist z.B ein äquivalenter TFM von `netcore451`.

| Zielframework           | TFM |
| -------------------------- | --- |
| .NET 5 (und .NET Core)     | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp3.0<br>netcoreapp3.1<br>net5.0* |
| .NET Standard              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard2.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Windows Store              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| Universelle Windows-Plattform | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

\* Die TFMs in .NET 5.0 und höher enthalten betriebssystemspezifische Varianten. Weitere Informationen finden Sie im folgenden Abschnitt [Betriebssystemspezifische TFMs in .NET 5](#net-5-os-specific-tfms).

### <a name="net-5-os-specific-tfms"></a>Betriebssystemspezifische TFMs in .NET 5

Für jeden TFM in .NET 5.0 und höher, z. B. `net5.0`, gibt es TFM-Varianten, die betriebssystemspezifische Bindungen enthalten. Diese Varianten sind in der folgenden Tabelle aufgeführt.

| Betriebssystemspezifisches Format | Beispiel        |
|--------------------|----------------|
| \<base-tfm>-android | net5.0-android |
| \<base-tfm>-ios     | net5.0-ios     |
| \<base-tfm>-macos   | net5.0-macos   |
| \<base-tfm>-tvos    | net5.0-tvos    |
| \<base-tfm>-watchos | net5.0-watchos |
| \<base-tfm>-windows | net5.0-windows |

Sie können ebenfalls eine optionale Betriebssystemversion angeben, z. B. `net5.0-ios12.0`.

Weitere Informationen zu den TFMs in .NET 5 finden Sie unter [Namen der Zielframeworks in .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md).

## <a name="how-to-specify-a-target-framework"></a>Angeben eines Zielframeworks

Zielframeworks werden in einer Projektdatei angegeben. Wenn ein einzelnes Framework angegeben wird, verwenden Sie das Element **TargetFramework** . Die folgende Projektdatei einer Konsolen-App veranschaulicht, wie Sie .NET 5.0 als Zielframework festlegen:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Wenn Sie mehrere Zielframeworks angeben, können Sie bedingt auf Assemblys für jedes Zielframework verweisen. Sie können in Ihrem Code bedingt mit diesen Assemblys kompilieren, indem Sie die Präprozessorsymbole mit *wenn-dann-sonst* -Logik verwenden.

Die folgende Bibliotheksprojektdatei ist auf APIs von .NET Standard (`netstandard1.4`) und des .NET Framework (`net40` und `net45`) ausgerichtet. Verwenden Sie das Element **TargetFrameworks** im Plural für mehrer Zielframeworks. Die `Condition`-Attribute enthalten implementierungsspezifische Pakete, wenn die Bibliothek für die zwei .NET Framework-TFMs kompiliert wird:

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

In Ihrer Bibliothek oder App schreiben Sie mithilfe von [Präprozessoranweisungen](../csharp/language-reference/preprocessor-directives/preprocessor-if.md) Bedingungscode, um für die verschiedenen Zielframeworks zu kompilieren:

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

Das Buildsystem beachtet Präprozessorsymbole, die Zielframeworks darstellen, die in der Tabelle [Unterstützte Zielframeworkversionen](#supported-target-frameworks) aufgelistet sind, wenn Sie Projekte im SDK-Format verwenden. Wenn Sie ein Symbol verwenden, das einen .NET Standard-, .NET Core- oder .NET 5-TFM darstellt, ersetzen Sie Punkte und Bindestriche durch einen Unterstrich, und ändern Sie Klein- in Großbuchstaben (das Symbol für `netstandard1.4` ist z. B. `NETSTANDARD1_4`).

Hier finden Sie eine vollständige Liste der Präprozessorsymbole für .NET-Zielframeworks:

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Veraltete Zielframeworks

Die folgenden Zielframeworks sind veraltet. Pakete, die auf diese Zielframeworks ausgelegt sind, sollten in das jeweilige Nachfolgeframework migriert werden.

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
