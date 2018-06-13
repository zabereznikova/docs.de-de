---
title: 'Gewusst wie: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen'
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
ms.openlocfilehash: 7638c6c9af5394838ac584e4dd9a9ca4cfbf8af0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547926"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Gewusst wie: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen
Sie können eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendung über die meisten Webserver bereitstellen, solange diese mit den erforderlichen [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)]-Typen konfiguriert werden. Standardmäßig wird [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] mit diesen [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen konfiguriert, [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] und [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] jedoch nicht.  
  
 In diesem Thema wird beschrieben, wie Sie [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] und [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] zum Bereitstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen konfigurieren.  
  
  
> [!NOTE]
>  Sehen Sie sich die *UserAgent* Zeichenfolge in der Registrierung, um zu bestimmen, ob ein System .NET Framework installiert ist. Weitere Informationen und ein Skript, überprüft der *UserAgent* Zeichenfolge zu bestimmen, ob .NET Framework auf einem System installiert ist, finden Sie unter [erkennen, ob die .NET Framework 3.0 installiert ist](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).  
  
<a name="content_expiration"></a>   
## <a name="adjust-the-content-expiration-setting"></a>Anpassen der Einstellung für die Gültigkeitsdauer des Inhalts  
 Sie sollten die Einstellung für die Inhaltsgültigkeitsdauer auf 1 Minute setzen. Die folgende Prozedur zeigt, wie Sie dies in [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] erreichen.  
  
1.  Klicken Sie auf das Menü **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie anschließend auf **Internetinformationsdienste-Manager**. Sie können diese Anwendung auch über die Befehlszeile starten, indem Sie den Befehl „%SystemRoot%\system32\inetsrv\iis.msc“ verwenden.  
  
2.  Erweitern Sie die [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]-Struktur, bis Sie den Knoten **Standardwebsite** gefunden haben.  
  
3.  Klicken Sie mit der rechten Maustaste auf **Standardwebsite**, und wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.  
  
4.  Wählen Sie die Registerkarte **HTTP-Header**, und klicken Sie auf „Inhalt läuft ab und wird ungültig“.  
  
5.  Setzen Sie die Ablaufzeit auf 1 Minute.  
  
<a name="register_mime_types"></a>   
## <a name="register-mime-types-and-file-extensions"></a>Registrieren von MIME-Typen und -Dateierweiterungen  
 Sie müssen mehrere [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen und -Dateierweiterungen registrieren, damit der Browser auf dem Clientsystem den richtigen Handler laden kann. Sie müssen die folgenden Typen hinzufügen:  
  
|Erweiterung|MIME-Typ|  
|---------------|---------------|  
|MANIFEST|application/manifest|  
|XAML|application/xaml+xml|  
|APPLICATION|application/x-ms-application|  
|XBAP|application/x-ms-xbap|  
|DEPLOY|application/octet-stream|  
|XPS|application/vnd.ms-xpsdocument|  
  
> [!NOTE]
>  Sie müssen auf Clientsystemen keine [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen oder -Dateierweiterungen registrieren. Sie werden automatisch registriert, bei der Installation von Microsoft .NET Framework.  
  
 Im folgende Beispiel für Microsoft Visual Basic Scripting Edition (VBScript) fügt automatisch die erforderlichen [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] Typen [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]. Um das Skript zu verwenden, kopieren Sie den Code in eine VBS-Datei auf dem Server. Führen Sie das Skript dann aus, indem Sie die Datei über die Befehlszeile oder durch Doppelklicken auf die Datei im [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)] ausführen.  
  
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
>  Wenn Sie dieses Skript mehrfach ausführen, werden in der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- bzw. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-Metabasis mehrere [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Zuordnungseinträge erstellt.  
  
 Nachdem Sie dieses Skript ausgeführt haben, kann es sein, dass Sie in der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- oder [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-[!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)] keine zusätzlichen [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen sehen. Diese [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen wurden der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- bzw. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-Metabasis jedoch hinzugefügt. Das folgende Skript zeigt alle [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]-Typen in der [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]- bzw. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]-Metabasis an.  
  
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
  
 Speichern Sie das Skript als `.vbs`-Datei (z. B. `DiscoverIISMimeTypes.vbs`), und führen Sie es an der Eingabeaufforderung aus, indem Sie den folgenden Befehl verwenden:  
  
 `cscript DiscoverIISMimeTypes.vbs`
