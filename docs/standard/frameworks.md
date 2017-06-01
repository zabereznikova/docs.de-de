---
title: Zielframeworks | Microsoft-Dokumentation
description: "Informationen zu Zielframeworks für .NET Core-Anwendungen und -Bibliotheken."
keywords: .NET, .NET Core, Framework, TFM
author: richlander
ms.author: mairaw
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
ms.translationtype: Machine Translation
ms.sourcegitcommit: 45835eb80642253f80ea630ae9db1ac766b72b9c
ms.openlocfilehash: 11c1f11e4f8354b7573d03e680cf4a8a16fa26d9
ms.contentlocale: de-de
ms.lasthandoff: 05/11/2017

---

# <a name="target-frameworks"></a>Zielframeworks

*Frameworks* definieren die Objekte, Methoden und Tools, mit denen Sie Apps und Bibliotheken erstellen. .NET Framework wird verwendet, um Apps und Bibliotheken zu erstellen, die in erster Linie auf Systemen mit Windows-Betriebssystemen ausgeführt werden. .NET Core umfasst ein Framework, mit dem Sie Apps und Bibliotheken erstellen können, die auf einer Vielzahl von Betriebssystemen ausgeführt werden.

Die Begriffe *Framework* und *Plattform* sind manchmal verwirrend, je nachdem, wie sie verwendet werden. Erschwerend kommt hinzu, dass der Begriff *Plattform* in unterschiedlichen Kontexten verschiedene Bedeutungen hat. Im Kontext der Erstellung von Apps und Bibliotheken spricht man beispielsweise vom „.NET Core-Framework“, im Kontext der Ausführung von App- und Bibliothekscode wird dasselbe Konzept aber auch als „.NET Core-Plattform“ bezeichnet. Eine *Computing-Plattform* beschreibt, *wo und wie* eine Anwendung ausgeführt wird. Da .NET Core Code mit der [.NET Core Common Language Runtime (CoreCLR)](https://github.com/dotnet/coreclr) ausführt, handelt es sich dabei auch um eine Plattform. Dasselbe gilt für .NET Framework, das mit der [Common Language Runtime (CLR)](clr.md) App- und Bibliothekscode ausführt, der mit Frameworkobjekten, Methoden und Tools von .NET Framework entwickelt wurde. Sie werden in der Dokumentation häufig auf den Begriff „plattformübergreifend“ treffen. Wenn Sie den Begriff lesen, sollten Sie aber an „betriebssystem- und architekturübergreifend (x86, x64, arm)“ denken, denn in diesem Sinne wird der Begriff vom Autor in der Regel verwendet.

Die Objekte und Methoden des Frameworks werden als Application Programming Interfaces (APIs) bezeichnet. Framework-APIs dienen in [Visual Studio](https://www.visualstudio.com/), [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/), [Visual Studio Code](https://code.visualstudio.com/) und anderen integrierten Entwicklungsumgebungen (IDEs) und Editoren dazu, den richtigen Satz von Objekten und Methoden für die Entwicklung bereitzustellen. Frameworks werden auch in [NuGet](https://www.nuget.org/) für die Erzeugung und die Nutzung von NuGet-Paketen verwendet, um sicherzustellen, dass Sie die richtigen Pakete für die Frameworks erzeugen und verwenden, für die Sie Ihre App oder Bibliothek auslegen möchten.

Wenn Sie *ein bestimmtes Framework* oder mehrere Framework als Ziel auswählen, haben Sie entschieden, welche API-Sätze und welche Versionen dieser APIs Sie verwenden möchten. Auf Frameworks wird auf verschiedene Weise verwiesen: anhand des Produktnamens, anhand der langen oder kurzen Form des Frameworknamens und anhand der Familie.

## <a name="referring-to-frameworks"></a>Verweisen auf Frameworks

Es gibt mehrere Möglichkeiten, auf Frameworks zu verweisen. Die meisten davon werden in der gesamten .NET Core-Dokumentation verwendet. Am Beispiel von .NET Framework 4.6.2. werden folgende Formate verwendet:

**Verweisen auf ein Produkt**

Sie können auf eine .NET-Plattform oder -Laufzeit verweisen. Beide Angaben sind gleichermaßen gültig.

* .NET Framework 4.6.2
* .NET 4.6.2

**Verweisen auf ein Framework**

Sie können mithilfe der langen oder kurzen Form des Zielframeworkmonikers auf ein Framework oder eine Frameworkzielplattform verweisen. Beide Angaben sind gleichermaßen gültig.

* `.NETFramework,Version=4.6.2`
* `net462`

**Verweisen auf eine Frameworkfamilie**

Sie können mithilfe der langen oder kurzen Form der Framework-ID auf eine Frameworkfamilie verweisen. Beide Angaben sind gleichermaßen gültig.

* `.NETFramework`
* `net`

## <a name="latest-framework-versions"></a>Neueste Framework Versionen

Die folgende Tabelle gibt an, welche Frameworks Sie verwenden können, wie auf die Frameworks verwiesen wird und welche Version der [.NET-Standardbibliothek](library.md) von den Frameworks implementiert wird. Diese Frameworkversionen sind die neuesten stabilen Versionen. Vorabversionen werden nicht angezeigt.

| Framework             | Letzte Version | Zielframeworkmoniker (Target Framework Moniker, TFM) | Kompakter Zielframeworkmoniker (Target Framework Moniker, TFM) | .NET-Standardversion | Metapaket |
| :-------------------: | :------------: | :----------------------------: | :------------------------------------: | :-------------------: | :---------: |
| .NET-Standard         | 1.6.1          | .NETStandard,Version=1.6       | netstandard1.6                         | Nicht zutreffend                   | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) |
| .NET Core-Anwendung | 1.1.1          | .NETCoreApp,Version=1.1        | netcoreapp1.1                          | 1.6                   | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) |
| .NET Framework        | 4.6.2          | .NETFramework,Version=4.6.2    | net462                                 | 1.5                   | Nicht zutreffend |

## <a name="supported-frameworks"></a>Unterstützte Frameworks

Ein Framework wird in der Regel durch einen kurzen Zielframeworkmoniker oder *TFM* referenziert. In .NET Standard kann dies auch mit *TxM* generalisiert werden, um mit einen einzigen Verweis mehrere Frameworks zu referenzieren. Die NuGet-Clients unterstützen die folgenden Frameworks. Äquivalente werden in Klammern angegeben (`[]`).

| Name                       | Abkürzung | TFMs/TxMs                                    |
| -------------------------- | ------------ | -------------------------------------------- |
| .NET-Standard              | netstandard  | netstandard1.0                               |
|                            |              | netstandard1.1                               |
|                            |              | netstandard1.2                               |
|                            |              | netstandard1.3                               |
|                            |              | netstandard1.4                               |
|                            |              | netstandard1.5                               |
|                            |              | netstandard1.6                               |
| .NET Core                  | netcoreapp   | netcoreapp1.0                                |
|                            |              | netcoreapp1.1                                |
| .NET Framework             | net          | net11                                        |
|                            |              | net20                                        |
|                            |              | net35                                        |
|                            |              | net40                                        |
|                            |              | net403                                       |
|                            |              | net45                                        |
|                            |              | net451                                       |
|                            |              | net452                                       |
|                            |              | net46                                        |
|                            |              | net461                                       |
|                            |              | net462                                       |
| Windows Store              | netcore      | netcore [netcore45]                          |
|                            |              | netcore45 [win, win8]                        |
|                            |              | netcore451 [win81]                           |
| .NET Micro Framework       | netmf        | netmf                                        |
| Silverlight                | sl           | sl4                                          |
|                            |              | sl5                                          |
| Windows Phone              | wp           | wp [wp7]                                     |
|                            |              | wp7                                          |
|                            |              | wp75                                         |
|                            |              | wp8                                          |
|                            |              | wp81                                         |
|                            |              | wpa81                                        |
| Universelle Windows-Plattform | uap          | uap [uap10.0]                                |
|                            |              | uap10.0 [win10] [netcore50]                  |

## <a name="deprecated-frameworks"></a>Veraltete Frameworks

Die folgenden Frameworks sind veraltet. Pakete, die für diese Frameworks ausgelegt sind, sollten zur jeweiligen Ersetzung migriert werden.

| Veraltetes Framework | Ersetzung |
| -------------------- | ----------- |
| aspnet50             | netcoreapp  |
| aspnetcore50         |             |
| dnxcore50            |             |
| dnx                  |             |
| dnx45                |             |
| dnx451               |             |
| dnx452               |             |
| dotnet               | netstandard |
| dotnet50             |             |
| dotnet51             |             |
| dotnet52             |             |
| dotnet53             |             |
| dotnet54             |             |
| dotnet55             |             |
| dotnet56             |             |
| netcore50            | uap10.0     |
| win                  | netcore45   |
| win8                 | netcore45   |
| win81                | netcore451  |
| win10                | uap10.0     |
| winrt                | netcore45   |

## <a name="precedence"></a>Rangfolge

Eine Reihe von Frameworks sind miteinander verwandt und kompatibel, aber nicht notwendigerweise äquivalent:

| Framework                        | Darf verwenden   |
| -------------------------------- | --------- |
| uap (Universelle Windows-Plattform) | win81     |
|                                  | wpa81     |
|                                  | netcore50 |
| win (Windows Store)              | winrt     |
|                                  | winrt45   |

## <a name="net-standard"></a>.NET-Standard

[.NET Standard](https://github.com/dotnet/standard) vereinfacht Verweise zwischen binärkompatiblen Frameworks, wodurch ein einzelnes Zielframeworks auf eine Kombination aus anderen Frameworks verweisen kann. Weitere Informationen finden Sie im Thema [.NET-Standardbibliothek](library.md).

Das NuGet-Tool [ Get Nearest Framework](http://nugettoolsdev.azurewebsites.net/) simuliert die für die Auswahl eines Frameworks aus mehreren verfügbaren Frameworkobjekten in einem Paket verwendete NuGet-Logik, basierend auf dem Framework des Projekts. Um das Tool zu verwenden, geben Sie ein Projektframework sowie ein oder mehrere Paketframeworks ein. Klicken Sie auf die Schaltfläche **Senden**. Das Tool gibt an, ob die aufgelisteten Paketframeworks mit dem angegebenen Projektframework kompatibel sind.

## <a name="portable-class-libraries"></a>Portable Klassenbibliotheken

Informationen zu portablen Klassenbibliotheken finden Sie im Abschnitt [Portable Klassenbibliotheken](https://docs.microsoft.com/nuget/schema/target-frameworks#portable-class-libraries) des Themas *Zielframework* in der NuGet-Dokumentation. Stephen Cleary hat ein Tool erstellt, das die unterstützten PCLs auflistete. Weitere Informationen finden Sie unter [Frameworkprofile in .NET](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html).

