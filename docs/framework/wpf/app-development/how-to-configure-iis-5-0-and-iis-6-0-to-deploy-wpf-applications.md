---
title: 'Gewusst wie: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ab1d7223299697a4be10ba5b35bc90b120603d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="faa9c-102">Gewusst wie: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="faa9c-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>
<span data-ttu-id="faa9c-103">Sie können eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendung über die meisten Webserver bereitstellen, solange diese mit den erforderlichen [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)]-Typen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="faa9c-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] types.</span></span> <span data-ttu-id="faa9c-104">Standardmäßig wird [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] mit diesen [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen konfiguriert, [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] und [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="faa9c-104">By default, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] is configured with these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types, but [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] are not.</span></span>  
  
 <span data-ttu-id="faa9c-105">In diesem Thema wird beschrieben, wie Sie [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] und [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] zum Bereitstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="faa9c-105">This topic describes how to configure [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  
  
  
> [!NOTE]
>  <span data-ttu-id="faa9c-106">Sie können die *UserAgent*-Zeichenfolge in der Registrierung überprüfen, um zu ermitteln, ob auf einem System [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="faa9c-106">You can check the *UserAgent* string in the registry to determine whether a system has [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installed.</span></span> <span data-ttu-id="faa9c-107">Ausführliche Informationen und ein Skript, das die *UserAgent*-Zeichenfolge überprüft, um zu ermitteln, ob auf einem System [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installiert ist, finden Sie unter [Gewusst wie: Erkennen einer .NET Framework 3.0-Installation](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="faa9c-107">For details and a script that examines the *UserAgent* string to determine whether [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="faa9c-108">Anpassen der Einstellung für die Gültigkeitsdauer des Inhalts</span><span class="sxs-lookup"><span data-stu-id="faa9c-108">Adjust the Content Expiration Setting</span></span>  
 <span data-ttu-id="faa9c-109">Sie sollten die Einstellung für die Inhaltsgültigkeitsdauer auf 1 Minute setzen.</span><span class="sxs-lookup"><span data-stu-id="faa9c-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="faa9c-110">Die folgende Prozedur zeigt, wie Sie dies in [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] erreichen.</span><span class="sxs-lookup"><span data-stu-id="faa9c-110">The following procedure outlines how to do this with [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span>  
  
1.  <span data-ttu-id="faa9c-111">Klicken Sie auf das Menü **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie anschließend auf **Internetinformationsdienste-Manager**.</span><span class="sxs-lookup"><span data-stu-id="faa9c-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="faa9c-112">Sie können diese Anwendung auch über die Befehlszeile starten, indem Sie den Befehl „%SystemRoot%\system32\inetsrv\iis.msc“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="faa9c-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>  
  
2.  <span data-ttu-id="faa9c-113">Erweitern Sie die [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]-Struktur, bis Sie den Knoten **Standardwebsite** gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="faa9c-113">Expand the [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] tree until you find the **Default Web site** node.</span></span>  
  
3.  <span data-ttu-id="faa9c-114">Klicken Sie mit der rechten Maustaste auf **Standardwebsite**, und wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="faa9c-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>  
  
4.  <span data-ttu-id="faa9c-115">Wählen Sie die Registerkarte **HTTP-Header**, und klicken Sie auf „Inhalt läuft ab und wird ungültig“.</span><span class="sxs-lookup"><span data-stu-id="faa9c-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>  
  
5.  <span data-ttu-id="faa9c-116">Setzen Sie die Ablaufzeit auf 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="faa9c-116">Set the content to expire after 1 minute.</span></span>  
  
<a name="register_mime_types"></a>   
## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="faa9c-117">Registrieren von MIME-Typen und -Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="faa9c-117">Register MIME Types and File Extensions</span></span>  
 <span data-ttu-id="faa9c-118">Sie müssen mehrere [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen und -Dateierweiterungen registrieren, damit der Browser auf dem Clientsystem den richtigen Handler laden kann.</span><span class="sxs-lookup"><span data-stu-id="faa9c-118">You must register several [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="faa9c-119">Sie müssen die folgenden Typen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="faa9c-119">You need to add the following types:</span></span>  
  
|<span data-ttu-id="faa9c-120">Erweiterung</span><span class="sxs-lookup"><span data-stu-id="faa9c-120">Extension</span></span>|<span data-ttu-id="faa9c-121">MIME-Typ</span><span class="sxs-lookup"><span data-stu-id="faa9c-121">MIME Type</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="faa9c-122">MANIFEST</span><span class="sxs-lookup"><span data-stu-id="faa9c-122">.manifest</span></span>|<span data-ttu-id="faa9c-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="faa9c-123">application/manifest</span></span>|  
|<span data-ttu-id="faa9c-124">XAML</span><span class="sxs-lookup"><span data-stu-id="faa9c-124">.xaml</span></span>|<span data-ttu-id="faa9c-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="faa9c-125">application/xaml+xml</span></span>|  
|<span data-ttu-id="faa9c-126">APPLICATION</span><span class="sxs-lookup"><span data-stu-id="faa9c-126">.application</span></span>|<span data-ttu-id="faa9c-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="faa9c-127">application/x-ms-application</span></span>|  
|<span data-ttu-id="faa9c-128">XBAP</span><span class="sxs-lookup"><span data-stu-id="faa9c-128">.xbap</span></span>|<span data-ttu-id="faa9c-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="faa9c-129">application/x-ms-xbap</span></span>|  
|<span data-ttu-id="faa9c-130">DEPLOY</span><span class="sxs-lookup"><span data-stu-id="faa9c-130">.deploy</span></span>|<span data-ttu-id="faa9c-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="faa9c-131">application/octet-stream</span></span>|  
|<span data-ttu-id="faa9c-132">XPS</span><span class="sxs-lookup"><span data-stu-id="faa9c-132">.xps</span></span>|<span data-ttu-id="faa9c-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="faa9c-133">application/vnd.ms-xpsdocument</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="faa9c-134">Sie müssen auf Clientsystemen keine [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen oder -Dateierweiterungen registrieren.</span><span class="sxs-lookup"><span data-stu-id="faa9c-134">You do not need to register [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types or file extensions on client systems.</span></span> <span data-ttu-id="faa9c-135">Die Registrierung wird automatisch beim Installieren von [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="faa9c-135">They are registered automatically when you install [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)].</span></span>  
  
 <span data-ttu-id="faa9c-136">Im folgenden [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)]-Beispiel werden die erforderlichen [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="faa9c-136">The following [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] sample automatically adds the necessary [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types to [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span> <span data-ttu-id="faa9c-137">Um das Skript zu verwenden, kopieren Sie den Code in eine VBS-Datei auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="faa9c-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="faa9c-138">Führen Sie das Skript dann aus, indem Sie die Datei über die Befehlszeile oder durch Doppelklicken auf die Datei im [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)] ausführen.</span><span class="sxs-lookup"><span data-stu-id="faa9c-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>  
  
```  
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
  
' Get the mimemap object   
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
    Redim Preserve MimeMapArray(i)   
    Set MimeMapArray(i) = CreateObject("MimeMap")   
    MimeMapArray(i).Extension = Ext   
    MimeMapArray(i).MimeType = MType   
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray  
    MimeMapObj.SetInfo  
  
End Sub  
```  
  
> [!NOTE]
>  <span data-ttu-id="faa9c-139">Wenn Sie dieses Skript mehrfach ausführen, werden in der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- bzw. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-Metabasis mehrere [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Zuordnungseinträge erstellt.</span><span class="sxs-lookup"><span data-stu-id="faa9c-139">Running this script multiple times creates multiple [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] map entries in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
 <span data-ttu-id="faa9c-140">Nachdem Sie dieses Skript ausgeführt haben, kann es sein, dass Sie in der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- oder [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-[!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)] keine zusätzlichen [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen sehen.</span><span class="sxs-lookup"><span data-stu-id="faa9c-140">After you have run this script, you may not see additional [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types from the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span></span> <span data-ttu-id="faa9c-141">Diese [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen wurden der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- bzw. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-Metabasis jedoch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="faa9c-141">However, these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types have been added to the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span> <span data-ttu-id="faa9c-142">Das folgende Skript zeigt alle [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen in der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- bzw. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-Metabasis an.</span><span class="sxs-lookup"><span data-stu-id="faa9c-142">The following script will display all the [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
```  
' This script lists the MIME types for an IIS Server.  
' To use this script, just double-click or execute it from a command line   
' by calling cscript.exe  
  
dim mimeMapEntry, allMimeMaps  
  
' Get the mimemap object.  
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")  
allMimeMaps = mimeMapEntry.GetEx("MimeMap")  
  
' Display the mappings in the table.  
For Each mimeMap In allMimeMaps  
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")  
Next  
```  
  
 <span data-ttu-id="faa9c-143">Speichern Sie das Skript als `.vbs`-Datei (z. B. `DiscoverIISMimeTypes.vbs`), und führen Sie es an der Eingabeaufforderung aus, indem Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="faa9c-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>  
  
 `cscript DiscoverIISMimeTypes.vbs`
