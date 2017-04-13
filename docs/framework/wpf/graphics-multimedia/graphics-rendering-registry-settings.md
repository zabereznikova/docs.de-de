---
title: "Registrierungseinstellungen f&#252;r das Rendern von Grafiken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Grafiken [WPF], Rendern"
  - "Rendern von Grafiken"
  - "Rendern von Grafiken, Registrierungseinstellungen"
  - "Rendern von Grafiken, Problembehandlung"
  - "Problembehandlung beim Rendern von Grafiken"
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Registrierungseinstellungen f&#252;r das Rendern von Grafiken
Dieses Thema enthält eine Übersicht über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Registrierungseinstellungen für das Rendern von Grafiken, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen beeinflussen.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="overview"></a>   
## Verwendung von Registrierungseinstellungen für das Rendern von Grafiken  
 Diese Registrierungseinstellungen werden für die Problembehandlung, das Debuggen sowie für den Produktsupport bereitgestellt.  Da Änderungen an der Registrierung sich auf alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen auswirken, sollten diese Registrierungsschlüssel von Ihrer Anwendung nie automatisch geändert werden. Auch während der Installation sollten keine Änderungen vorgenommen werden.  
  
<a name="xpdmandwddm"></a>   
## Was sind XPDM und WDDM?  
 Einige der Registrierungseinstellungen für das Rendern von Grafiken besitzen unterschiedliche Standardwerte. Dies hängt davon ab, ob Ihre Videokarte einen XPDM\-Treiber oder einen WDDM\-Treiber verwendet.  XPDM ist das [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]\-Anzeigetreibermodell, und WDDM ist das Windows\-Anzeigetreibermodell.  WDDM ist auf Computern unter [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] und [!INCLUDE[win7](../../../../includes/win7-md.md)] verfügbar.  XPDM ist auf Computern unter [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] und [!INCLUDE[TLA#tla_winnetsvrfam](../../../../includes/tlasharptla-winnetsvrfam-md.md)] verfügbar.  Weitere Informationen zu WDDM finden Sie unter [Windows Vista Display Driver Model Design Guide](http://go.microsoft.com/fwlink/?LinkId=178394).  
  
<a name="registry_settings"></a>   
## Registrierungseinstellungen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt vier Registrierungseinstellungen zum Steuern des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Rendering bereit:  
  
|Einstellung|Beschreibung|  
|-----------------|------------------|  
|**Option zum Deaktivieren der Hardwarebeschleunigung**|Gibt an, ob die Hardwarebeschleunigung aktiviert werden soll.|  
|**Maximaler Wert für Multisampling**|Gibt den Grad des Multisampling für das Antialiasing von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Inhalten an.|  
|**Einstellung für das erforderliche Videotreiberdatum**|Gibt an, ob das System die Hardwarebeschleunigung für Treiber deaktiviert, die vor November 2004 veröffentlicht wurden.|  
|**Option zum Verwenden der Referenz\-Rasterisierungsfunktion**|Gibt an, ob [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Referenz\-Rasterisierungsfunktion verwenden soll.|  
  
 Auf diese Einstellungen kann mit jedem externen Konfigurationsdienstprogramm zugegriffen werden, das auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Registrierungseinstellungen verweisen kann.  Diese Einstellungen lassen sich auch erstellen oder ändern, indem mithilfe des [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Registrierungs\-Editors direkt auf die Werte zugegriffen wird.  
  
<a name="disablehardwareacceleration"></a>   
## Option zum Deaktivieren der Hardwarebeschleunigung  
  
|Registrierungsschlüssel|Werttyp|  
|-----------------------------|-------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|DWORD|  
  
 Die **Option zum Deaktivieren der Hardwarebeschleunigung** ermöglicht Ihnen, die Hardwarebeschleunigung zum Debuggen und zu Testzwecken auszuschalten.  Wenn Sie Renderingartefakte in einer Anwendung finden, versuchen Sie, die Hardwarebeschleunigung auszuschalten.  Wenn das Artefakt verschwindet, könnte das Problem vom Videotreiber verursacht werden.  
  
 Die **Option zum Deaktivieren der Hardwarebeschleunigung** ist ein DWORD\-Wert, der entweder 0 oder 1 ist.  Der Wert 1 deaktiviert die Hardwarebeschleunigung.  Bei einem Wert von 0 \(null\) ist die Hardwarebeschleunigung aktiviert, vorausgesetzt, das System erfüllt die Anforderung für die Hardwarebeschleunigung. Weitere Informationen finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
<a name="maxmultisample"></a>   
## Maximaler Wert für Multisampling  
  
|Registrierungsschlüssel|Werttyp|  
|-----------------------------|-------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|DWORD|  
  
 Der **maximale Wert für Multisampling** ermöglicht es Ihnen, die maximale Menge für das Antialiasing von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Inhalt anzupassen.  Verwenden Sie diese Ebene, um [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Antialiasing in [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] zu deaktivieren oder in [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] zu aktivieren.  
  
 Der **maximale Wert für Multisampling** ist ein DWORD\-Wert, der zwischen 0 und 16 liegt.  Bei einem Wert von 0 ist angegeben, dass Multisample\-Antialiasing von 3\-D\-Inhalt deaktiviert werden soll, und bei einem Wert von 16 wird versucht, 16x\-Multisample\-Antialiasing zu verwenden, wenn dies von der Videokarte unterstützt wird.  Wenn Sie diesen Registrierungsschlüssel auf Computern mit XPDM\-Treibern festlegen, müssen Sie beachten, dass die Anwendungen wesentlich mehr Videospeicher benötigen, die Leistung des [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Rendering vermindert wird und dass unter Umständen Renderingfehler und Stabilitätsprobleme auftreten.  
  
 Wenn dieser Registrierungsschlüssel nicht festgelegt wird, ist der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Standardwert für XPDM\-Treiber 0 \(null\) und für WDDM\-Treiber 4.  
  
<a name="requiredvideodriverdatesetting"></a>   
## Einstellung für das erforderliche Videotreiberdatum  
  
|Registrierungsschlüssel|Werttyp|  
|-----------------------------|-------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|Zeichenfolge|  
  
 Im November 2004 wurde von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] eine neue Version der Richtlinien zum Testen von Treibern herausgegeben. Die nach diesem Datum erstellten Treiber bieten mehr Stabilität.  Standardmäßig verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Hardwarebeschleunigungspipeline für diese Treiber. Bei XPDM\-Treibern, die vor diesem Datum erstellt wurden, wird auf Softwarerendering zurückgegriffen.  
  
 Die **Einstellung für das erforderliche Videotreiberdatum** ermöglicht es Ihnen, einen alternativen minimalen Datumswert für XPDM\-Treiber anzugeben.  Sie sollten nur dann ein Datum vor November 2004 angeben, wenn Sie sicher sind, dass Ihr Videotreiber stabil genug ist, um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu unterstützen.  
  
 Für die erforderliche Einstellung für den Videotreiber wird eine Zeichenfolge im folgenden Format verwendet:  
  
||  
|-|  
|*JJJJ* `/` *MM* `/` *TT*|  
  
 Hierbei steht *YYYY* für die vierstellige Jahreszahl, *MM* für die zweistellige Monatszahl und *DD* für die zweistellige Tageszahl.  Wenn dieser Wert nicht festgelegt ist, verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] November 2004 als erforderliches Datum für den Videotreiber.  
  
<a name="usereferencerasterizeroption"></a>   
## Option zum Verwenden der Referenz\-Rasterisierungsfunktion  
  
|Registrierungsschlüssel|Werttyp|  
|-----------------------------|-------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|DWORD|  
  
 Die **Option zum Verwenden der Referenz\-Rasterisierungsfunktion** ermöglicht Ihnen, für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen simulierten Hardwarerenderingmodus zum Debuggen zu erzwingen: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wechselt in den Hardwaremodus, verwendet jedoch statt eines tatsächlichen Hardwaregeräts die Referenz\-Rasterisierungsfunktion d3dref9.dll der [!INCLUDE[TLA#tla_d3d](../../../../includes/tlasharptla-d3d-md.md)]\-Software.  
  
 Die Referenz\-Rasterisierungsfunktion ist sehr langsam, umgeht jedoch den Videotreiber, um so mögliche vom Treiber verursachte Renderingprobleme zu vermeiden.  Die Referenz\-Rasterisierungsfunktion können Sie also verwenden, um festzustellen, ob Renderingprobleme vom Treiber verursacht werden.  Die Datei d3dref9.dll muss sich an einem Speicherort befinden, an dem die Anwendung auf sie zugreifen kann, z. B. an einem beliebigen Speicherort im Systempfad oder im lokalen Verzeichnis der Anwendung.  
  
 Die **Option zum Verwenden der Referenz\-Rasterisierungsfunktion** verwendet einen DWORD\-Wert.  Ein Wert von 0 \(null\) gibt an, dass die Referenz\-Rasterisierungsfunktion nicht verwendet wird.  Jeder andere Wert ungleich 0 \(null\) zwingt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die Referenz\-Rasterisierungsfunktion zu verwenden.  
  
## Siehe auch  
 [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)