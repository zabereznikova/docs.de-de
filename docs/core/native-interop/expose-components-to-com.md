---
title: Verfügbarmachen von .NET Core-Komponenten in COM
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 8d9b8eb274777a0ed019a207c6e8610cc73ec390
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973316"
---
# <a name="exposing-net-core-components-to-com"></a>Verfügbarmachen von .NET Core-Komponenten in COM

In .NET Core wurde das Verfügbarmachen von .NET-Objekten für COM im Vergleich zum .NET Framework deutlich optimiert. Im Folgenden wird erläutert, wie Sie eine Klasse für COM verfügbar machen. In diesem Tutorial lernen Sie:

- Verfügbarmachen einer Klasse für COM in .NET Core
- Generieren eines COM-Servers bei der Erstellung einer .NET Core-Bibliothek
- Automatisches Generieren eines Manifests zur parallelen Serverausführung ohne COM-Registrierung

## <a name="prerequisites"></a>Erforderliche Komponenten

- Installieren Sie [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) oder eine neuere Version.

## <a name="create-the-library"></a>Erstellen der Bibliothek

Im ersten Schritt erstellen Sie die Bibliothek.

1. Erstellen Sie einen neuen Ordner, und führen Sie in diesem Ordner den folgenden Befehl aus:
    
    ```dotnetcli
    dotnet new classlib
    ```

2. Öffnen Sie `Class1.cs`.
3. Fügen Sie `using System.Runtime.InteropServices;` am Anfang der Datei ein.
4. Erstellen Sie eine Schnittstelle mit dem Namen `IServer`. Beispiel:

   [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]

5. Fügen Sie der Schnittstelle das `[Guid("<IID>")]`-Attribut mit der Schnittstellen-GUID für die COM-Schnittstelle hinzu, die Sie implementieren. Beispielsweise `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`. Diese GUID muss eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist. In Visual Studio können Sie eine GUID generieren. Rufen Sie dazu „Extras“ > „GUID erstellen“ auf, um das entsprechende Tool zu verwenden.
6. Fügen Sie der Schnittstelle das `[InterfaceType]`-Attribut hinzu, und geben Sie an, welche COM-Basisschnittstellen Ihre Schnittstelle implementieren soll.
7. Erstellen Sie eine Klasse mit dem Namen `Server`, die `IServer` implementiert.
8. Fügen Sie der Klasse das `[Guid("<CLSID>")]`-Attribut mit der Klassenbezeichner-GUID für die COM-Klasse hinzu, die Sie implementieren. Beispielsweise `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`. Diese GUID muss genau wie die Schnittstellen-GUID eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.
9. Fügen Sie der Schnittstelle und der Klasse das `[ComVisible(true)]`-Attribut hinzu.

> [!IMPORTANT]
> Anders als im .NET Framework müssen Sie in .NET Core die CLSID jeder Klasse angeben, die über COM aktivierbar sein soll.

## <a name="generate-the-com-host"></a>Generieren des COM-Hosts

1. Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableComHosting>true</EnableComHosting>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.
2. Erstellen Sie das Projekt.

Die Ausgabe enthält die Dateien `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` und `ProjectName.comhost.dll`.

## <a name="register-the-com-host-for-com"></a>Registrieren des COM-Hosts für COM

Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie `regsvr32 ProjectName.comhost.dll` aus. Dadurch werden alle verfügbaren .NET-Objekte bei COM registriert.

## <a name="enabling-regfree-com"></a>Aktivieren von COM ohne Registrierung

1. Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableRegFreeCom>true</EnableRegFreeCom>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.
2. Erstellen Sie das Projekt.

Die Ausgabe enthält nun auch die Datei `ProjectName.X.manifest`. Bei dieser Datei handelt es sich um das Manifest zur parallelen Ausführung, das ohne COM-Registrierung verwendet werden kann.

## <a name="sample"></a>Beispiel

Ein voll funktionsfähiges [Beispiel für COM-Server](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) finden Sie im GitHub-Repository „dotnet/samples“.

## <a name="additional-notes"></a>Zusätzliche Hinweise

Anders als im .NET Framework wird in .NET Core die Erstellung einer COM-Typbibliothek (TLB) aus einer .NET Core-Assembly nicht unterstützt. Die Anweisung besagt, dass Sie manuell eine IDL-Datei oder einen C++ Header für die nativen Deklarationen Ihrer Schnittstellen schreiben müssen.

Zusätzlich gelten für das Laden von .NET Framework und .NET Core in denselben Prozess Diagnoseeinschränkungen. Die erste Einschränkung ist das Debuggen von verwalteten Komponenten, da es nicht möglich ist, .NET Framework und .NET Core gleichzeitig zu debuggen. Zusätzlich teilen die beiden Runtimeinstanzen keine verwalteten Assemblys. Das bedeutet, dass es nicht möglich ist, die tatsächlichen .NET-Typen über zwei Runtimes freizugeben. Stattdessen unterliegen alle Interaktionen den verfügbar gemachten Verträgen zur COM-Schnittstelle.
