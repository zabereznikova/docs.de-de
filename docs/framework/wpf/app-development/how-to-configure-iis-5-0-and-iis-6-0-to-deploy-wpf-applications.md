---
title: 'Gewusst wie: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: d557ac6cd380edcbc93b5315f6356697817274bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740410"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Gewusst wie: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen

Sie können eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung von den meisten Webservern bereitstellen, sofern Sie mit den entsprechenden Multipurpose Internet Mail Extensions (MIME)-Typen konfiguriert sind. Standardmäßig ist Microsoft Internetinformationsdienste (IIS) 7,0 mit diesen MIME-Typen konfiguriert, Microsoft Internetinformationsdienste (IIS) 5,0 und Microsoft Internetinformationsdienste (IIS) 6,0 hingegen nicht.

In diesem Thema wird beschrieben, wie Sie Microsoft Internetinformationsdienste (IIS) 5,0 und Microsoft Internetinformationsdienste (IIS) 6,0 zum Bereitstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen konfigurieren.

> [!NOTE]
> Sie können die *userAgent* -Zeichenfolge in der Registrierung überprüfen, um zu bestimmen, ob ein System .NET Framework installiert ist. Ausführliche Informationen und ein Skript, das die *userAgent* -Zeichenfolge untersucht, um zu bestimmen, ob .NET Framework auf einem System installiert ist, finden Sie unter [erkennen, ob die .NET Framework 3,0 installiert ist](how-to-detect-whether-the-net-framework-3-0-is-installed.md).

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a>Anpassen der Einstellung für die Gültigkeitsdauer des Inhalts

Sie sollten die Einstellung für die Inhaltsgültigkeitsdauer auf 1 Minute setzen. Im folgenden Verfahren wird beschrieben, wie dies mit IIS durchzuführen ist.

1. Klicken Sie auf das Menü **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie anschließend auf **Internetinformationsdienste-Manager**. Sie können diese Anwendung auch über die Befehlszeile starten, indem Sie den Befehl „%SystemRoot%\system32\inetsrv\iis.msc“ verwenden.

2. Erweitern Sie die IIS-Struktur, bis Sie den **Standard Website** Knoten gefunden haben.

3. Klicken Sie mit der rechten Maustaste auf **Standardwebsite**, und wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.

4. Wählen Sie die Registerkarte **HTTP-Header**, und klicken Sie auf „Inhalt läuft ab und wird ungültig“.

5. Setzen Sie die Ablaufzeit auf 1 Minute.

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a>Registrieren von MIME-Typen und -Dateierweiterungen

Sie müssen mehrere MIME-Typen und-Dateierweiterungen registrieren, damit der Browser auf dem Client System den richtigen Handler laden kann. Sie müssen die folgenden Typen hinzufügen:

|Erweiterung|MIME-Typ|
|---------------|---------------|
|.manifest|application/manifest|
|XAML|application/xaml+xml|
|APPLICATION|application/x-ms-application|
|XBAP|application/x-ms-xbap|
|DEPLOY|application/octet-stream|
|XPS|application/vnd.ms-xpsdocument|

> [!NOTE]
> Sie müssen keine MIME-Typen oder Dateierweiterungen auf Client Systemen registrieren. Sie werden automatisch registriert, wenn Sie Microsoft .NET Framework installieren.

Im folgenden Microsoft Visual Basic Scripting Edition-Beispiel (VBScript) werden IIS automatisch die erforderlichen MIME-Typen hinzugefügt. Um das Skript zu verwenden, kopieren Sie den Code in eine VBS-Datei auf dem Server. Führen Sie dann das Skript aus, indem Sie die Datei über die Befehlszeile ausführen oder in Microsoft Windows-Explorer auf die Datei doppelklicken.

```vb
' This script adds the necessary Windows Presentation Foundation MIME types
' to an IIS Server.
' To use this script, just double-click or execute it from a command line.
' Running this script multiple times results in multiple entries in the IIS MimeMap.

Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec
Const ADS_PROPERTY_UPDATE = 2

' Set the MIME types to be added
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _
    "application/xaml+xml", ".application", "application/x-ms-application", _
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _
    ".xps", "application/vnd.ms-xpsdocument")

' Get the MimeMap object
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")

' Call AddMimeType for every pair of extension/MIME type
For counter = 0 to UBound(MimeTypesToAddArray) Step 2
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)
Next

' Create a Shell object
Set WshShell = CreateObject("WScript.Shell")

' Stop and Start the IIS Service
Set oExec = WshShell.Exec("net stop w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = WshShell.Exec("net start w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = Nothing

' Report status to user
WScript.Echo "Windows Presentation Foundation MIME types have been registered."

' AddMimeType Sub
Sub AddMimeType (Ext, MType)

    ' Get the mappings from the MimeMap property.
    MimeMapArray = MimeMapObj.GetEx("MimeMap")

    ' Add a new mapping.
    i = UBound(MimeMapArray) + 1
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> Wenn Sie dieses Skript mehrmals ausführen, werden mehrere MIME-Zuordnungs Einträge in der Microsoft Internetinformationsdienste (IIS) 5,0-oder Microsoft Internetinformationsdienste (IIS) 6,0-Metabase erstellt.

Nachdem Sie dieses Skript ausgeführt haben, werden möglicherweise keine weiteren MIME-Typen aus der Microsoft Internetinformationsdienste (IIS) 5,0 oder Microsoft Internetinformationsdienste (IIS) 6,0 Microsoft Management Console (MMC) angezeigt. Diese MIME-Typen wurden jedoch der Metabase Microsoft Internetinformationsdienste (IIS) 5,0 oder Microsoft Internetinformationsdienste (IIS) 6,0 hinzugefügt. Im folgenden Skript werden alle MIME-Typen in der Microsoft Internetinformationsdienste (IIS) 5,0-oder Microsoft Internetinformationsdienste (IIS) 6,0-Metabase angezeigt.

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

Speichern Sie das Skript als `.vbs`-Datei (z. B. `DiscoverIISMimeTypes.vbs`), und führen Sie es an der Eingabeaufforderung aus, indem Sie den folgenden Befehl verwenden:

```console
cscript DiscoverIISMimeTypes.vbs
```
