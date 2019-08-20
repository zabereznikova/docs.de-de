---
title: 'Vorgehensweise: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen'
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
ms.openlocfilehash: 3a9bf79a9d505fef53b62cb589920adcf95ae92a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69611503"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="4c165-102">Vorgehensweise: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="4c165-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="4c165-103">Sie können eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung von den meisten Webservern bereitstellen, sofern Sie mit den entsprechenden Multipurpose Internet Mail Extensions (MIME)-Typen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="4c165-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate Multipurpose Internet Mail Extensions (MIME) types.</span></span> <span data-ttu-id="4c165-104">Standardmäßig ist Microsoft Internetinformationsdienste (IIS) 7,0 mit diesen MIME-Typen konfiguriert, Microsoft Internetinformationsdienste (IIS) 5,0 und Microsoft Internetinformationsdienste (IIS) 6,0 hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="4c165-104">By default, Microsoft Internet Information Services (IIS) 7.0 is configured with these MIME types, but Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 are not.</span></span>

<span data-ttu-id="4c165-105">In diesem Thema wird beschrieben, wie Sie Microsoft Internetinformationsdienste (IIS) 5,0 und Microsoft Internetinformationsdienste (IIS) 6,0 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Bereitstellen von Anwendungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c165-105">This topic describes how to configure Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="4c165-106">Sie können die *userAgent* -Zeichenfolge in der Registrierung überprüfen, um zu bestimmen, ob ein System .NET Framework installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4c165-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="4c165-107">Ausführliche Informationen und ein Skript, das die *userAgent* -Zeichenfolge untersucht, um zu bestimmen, ob .NET Framework auf einem System installiert ist, finden Sie unter [erkennen, ob die .NET Framework 3,0 installiert ist](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="4c165-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="4c165-108">Anpassen der Einstellung für die Gültigkeitsdauer des Inhalts</span><span class="sxs-lookup"><span data-stu-id="4c165-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="4c165-109">Sie sollten die Einstellung für die Inhaltsgültigkeitsdauer auf 1 Minute setzen.</span><span class="sxs-lookup"><span data-stu-id="4c165-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="4c165-110">Im folgenden Verfahren wird beschrieben, wie dies mit IIS durchzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="4c165-110">The following procedure outlines how to do this with IIS.</span></span>

1. <span data-ttu-id="4c165-111">Klicken Sie auf das Menü **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie anschließend auf **Internetinformationsdienste-Manager**.</span><span class="sxs-lookup"><span data-stu-id="4c165-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="4c165-112">Sie können diese Anwendung auch über die Befehlszeile starten, indem Sie den Befehl „%SystemRoot%\system32\inetsrv\iis.msc“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c165-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="4c165-113">Erweitern Sie die IIS-Struktur, bis Sie den **Standard Website** Knoten gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="4c165-113">Expand the IIS tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="4c165-114">Klicken Sie mit der rechten Maustaste auf **Standardwebsite**, und wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="4c165-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="4c165-115">Wählen Sie die Registerkarte **HTTP-Header**, und klicken Sie auf „Inhalt läuft ab und wird ungültig“.</span><span class="sxs-lookup"><span data-stu-id="4c165-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="4c165-116">Setzen Sie die Ablaufzeit auf 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="4c165-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="4c165-117">Registrieren von MIME-Typen und -Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="4c165-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="4c165-118">Sie müssen mehrere MIME-Typen und-Dateierweiterungen registrieren, damit der Browser auf dem Client System den richtigen Handler laden kann.</span><span class="sxs-lookup"><span data-stu-id="4c165-118">You must register several MIME types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="4c165-119">Sie müssen die folgenden Typen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4c165-119">You need to add the following types:</span></span>

|<span data-ttu-id="4c165-120">Erweiterung</span><span class="sxs-lookup"><span data-stu-id="4c165-120">Extension</span></span>|<span data-ttu-id="4c165-121">MIME-Typ</span><span class="sxs-lookup"><span data-stu-id="4c165-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="4c165-122">MANIFEST</span><span class="sxs-lookup"><span data-stu-id="4c165-122">.manifest</span></span>|<span data-ttu-id="4c165-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="4c165-123">application/manifest</span></span>|
|<span data-ttu-id="4c165-124">XAML</span><span class="sxs-lookup"><span data-stu-id="4c165-124">.xaml</span></span>|<span data-ttu-id="4c165-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="4c165-125">application/xaml+xml</span></span>|
|<span data-ttu-id="4c165-126">APPLICATION</span><span class="sxs-lookup"><span data-stu-id="4c165-126">.application</span></span>|<span data-ttu-id="4c165-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="4c165-127">application/x-ms-application</span></span>|
|<span data-ttu-id="4c165-128">XBAP</span><span class="sxs-lookup"><span data-stu-id="4c165-128">.xbap</span></span>|<span data-ttu-id="4c165-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="4c165-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="4c165-130">DEPLOY</span><span class="sxs-lookup"><span data-stu-id="4c165-130">.deploy</span></span>|<span data-ttu-id="4c165-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="4c165-131">application/octet-stream</span></span>|
|<span data-ttu-id="4c165-132">XPS</span><span class="sxs-lookup"><span data-stu-id="4c165-132">.xps</span></span>|<span data-ttu-id="4c165-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="4c165-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="4c165-134">Sie müssen keine MIME-Typen oder Dateierweiterungen auf Client Systemen registrieren.</span><span class="sxs-lookup"><span data-stu-id="4c165-134">You do not need to register MIME types or file extensions on client systems.</span></span> <span data-ttu-id="4c165-135">Sie werden automatisch registriert, wenn Sie Microsoft .NET Framework installieren.</span><span class="sxs-lookup"><span data-stu-id="4c165-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="4c165-136">Im folgenden Microsoft Visual Basic Scripting Edition-Beispiel (VBScript) werden IIS automatisch die erforderlichen MIME-Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c165-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary MIME types to IIS.</span></span> <span data-ttu-id="4c165-137">Um das Skript zu verwenden, kopieren Sie den Code in eine VBS-Datei auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="4c165-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="4c165-138">Führen Sie das Skript dann aus, indem Sie die Datei über die Befehlszeile oder durch Doppelklicken auf die Datei im [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)] ausführen.</span><span class="sxs-lookup"><span data-stu-id="4c165-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>

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
> <span data-ttu-id="4c165-139">Wenn Sie dieses Skript mehrmals ausführen, werden mehrere MIME-Zuordnungs Einträge in der Microsoft Internetinformationsdienste (IIS) 5,0-oder Microsoft Internetinformationsdienste (IIS) 6,0-Metabase erstellt.</span><span class="sxs-lookup"><span data-stu-id="4c165-139">Running this script multiple times creates multiple MIME map entries in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

<span data-ttu-id="4c165-140">Nachdem Sie dieses Skript ausgeführt haben, werden möglicherweise keine weiteren MIME-Typen aus der Microsoft Internetinformationsdienste (IIS) 5,0 oder Microsoft Internetinformationsdienste (IIS) 6,0 Microsoft Management Console (MMC) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c165-140">After you have run this script, you may not see additional MIME types from the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 Microsoft Management Console (MMC).</span></span> <span data-ttu-id="4c165-141">Diese MIME-Typen wurden jedoch der Metabase Microsoft Internetinformationsdienste (IIS) 5,0 oder Microsoft Internetinformationsdienste (IIS) 6,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c165-141">However, these MIME types have been added to the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span> <span data-ttu-id="4c165-142">Im folgenden Skript werden alle MIME-Typen in der Microsoft Internetinformationsdienste (IIS) 5,0-oder Microsoft Internetinformationsdienste (IIS) 6,0-Metabase angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c165-142">The following script will display all the MIME types in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

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

<span data-ttu-id="4c165-143">Speichern Sie das Skript als `.vbs`-Datei (z. B. `DiscoverIISMimeTypes.vbs`), und führen Sie es an der Eingabeaufforderung aus, indem Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="4c165-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
