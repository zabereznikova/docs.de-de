---
title: "ClearType-Registrierungseinstellungen | Microsoft Docs"
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
  - "ClearType, Registrierungseinstellungen"
  - "Typografie, ClearType-Registrierungseinstellungen"
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ClearType-Registrierungseinstellungen
Dieses Thema enthält eine Übersicht über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]\-Registrierungseinstellungen, die von den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen verwendet werden.  
  
   
  
<a name="overview"></a>   
## Übersicht über die Technologie  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen, die Text auf einem Anzeigegerät rendern, verwenden [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Funktionen, um eine bessere Lesbarkeit zu erreichen.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] ist eine von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] entwickelte Softwaretechnologie, mit der die Lesbarkeit auf LCD\-Bildschirmen \(Liquid Crystal Displays\) verbessert wird, z. B. auf Laptopbildschirmen, Pocket PC\-Bildschirmen und Flachbildschirmen.  Dazu greift [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] auf die einzelnen vertikalen Farbstreifenelemente in jedem Pixel auf einem LCD\-Bildschirm zu.  Weitere Informationen zu [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] finden Sie unter [Übersicht über ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 Text, der mit [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] gerendert wird, kann abhängig vom jeweiligen Anzeigegerät deutlich anders erscheinen.  So implementieren beispielsweise einige wenige Monitore die Farbstreifenelemente in der Reihenfolge Blau, Grün, Rot statt in der üblicheren Reihenfolge Rot, Grün, Blau \([!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]\).  
  
 Text, der mit [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] gerendert wird, kann auch deutlich anders erscheinen, wenn er von Personen mit unterschiedlichem Farbempfinden betrachtet wird.  Einige Personen können leichte Farbunterschiede besser erkennen als andere.  
  
 In all diesen Fällen müssen die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Features verändert werden, um die optimale Lesbarkeit für den einzelnen Betrachter zu erreichen.  
  
<a name="registry_settings"></a>   
## Registrierungseinstellungen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] legt vier Registrierungseinstellungen für das Steuern der [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Features fest:  
  
|Einstellung|Beschreibung|  
|-----------------|------------------|  
|[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Stufe|Beschreibt die Stufe der [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Farbklarheit.|  
|Gammastufe|Beschreibt die Stufe der Pixelfarbkomponente für ein Anzeigegerät.|  
|Pixelstruktur|Beschreibt die Pixelanordnung für ein Anzeigegerät.|  
|Textkontraststufe|Beschreibt die Kontraststufe für angezeigten Text.|  
  
 Auf diese Einstellungen kann mit einem externen Konfigurationsdienstprogramm zugegriffen werden, das auf die identifizierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Registrierungseinstellungen verweisen kann.  Diese Einstellungen lassen sich auch erstellen oder ändern, indem mithilfe des [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Registrierungs\-Editors direkt auf die Werte zugegriffen wird.  
  
 Wenn die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Registrierungseinstellungen nicht festgelegt sind \(dies ist der Standardstatus\), fragt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Systemparameterinformationen nach Einstellungen für die Schriftartglättung ab.  
  
> [!NOTE]
>  Informationen zur Auflistung von Anzeigegerätenamen finden Sie unter der `SystemParametersInfo`\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Funktion.  
  
<a name="ClearType_level"></a>   
## ClearType\-Stufe  
 Die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Ebene ermöglicht es, das Textrendering auf Grundlage des Farbempfindens und der Wahrnehmung einer Person anzupassen. Das Rendern von Text unter Verwendung der höchsten [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Ebene ist für einige Benutzer nicht unbedingt gleichbedeutend mit einer optimalen Lesbarkeit.  
  
 Die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Stufe ist ein Ganzzahlenwert im Bereich zwischen 0 und 100.   Die Standardstufe ist 100, d. h., [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] verwendet die maximale Kapazität der Farbstreifenelemente des Anzeigegeräts.  Bei einer [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Ebene von 0 wird Text in Graustufen gerendert.  Wenn Sie die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Stufe auf einen Wert zwischen 0 und 100 festlegen, können Sie eine Abstufung erreichen, die dem Farbempfinden des einzelnen Betrachters angemessen ist.  
  
### Registrierungseinstellung  
 Die Registrierungseinstellung für die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Stufe wird in einer individuellen Benutzereinstellung platziert, die einem bestimmten Anzeigegerätenamen entspricht:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für einen Benutzer wird ein `ClearTypeLevel`\-DWORD\-Wert definiert.  Die folgende Bildschirmabbildung zeigt die Registrierungs\-Editor\-Einstellung für die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Stufe.  
  
 ![ClearType&#45;Einstellungen im Registrierungs&#45;Editor](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen rendern Text in einem von zwei Modi: mit und ohne [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  Wenn Text ohne [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] gerendert wird, wird dies als Graustufenrendering bezeichnet.  
  
<a name="gamma_level"></a>   
## Gammastufe  
 Die Gammastufe bezieht sich auf die nicht lineare Beziehung zwischen einem Pixelwert und der Luminanz.  Die Gammastufeneinstellung sollte den physischen Eigenschaften des Anzeigegeräts entsprechen; andernfalls kann es zu Verzerrungen der gerenderten Ausgabe kommen.  So kann Text beispielsweise zu breit oder zu schmal erscheinen, oder es können Farbsäume an den Kanten vertikaler Symbolstriche auftreten.  
  
 Die Gammastufe ist ein Ganzzahlenwert im Bereich zwischen 1000 und 2200.  Der Standardwert ist 1900.  
  
### Registrierungseinstellung  
 Die Registrierungseinstellung für die Gammastufe ist eine lokale Computereinstellung, die einem bestimmten Anzeigegerätenamen entspricht:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für einen Benutzer wird ein `GammaLevel`\-DWORD\-Wert definiert.  Die folgende Bildschirmabbildung zeigt die Registrierungs\-Editor\-Einstellung für die Gammastufe.  
  
 ![ClearType&#45;Einstellungen im Registrierungs&#45;Editor](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="pixel_structure"></a>   
## Pixelstruktur  
 Die Pixelstruktur beschreibt den Pixeltyp eines Anzeigegeräts.  Die Pixelstruktur ist als einer von drei Typen definiert:  
  
|Typ|Wert|Beschreibung|  
|---------|----------|------------------|  
|Flach|0|Das Anzeigegerät hat keine Pixelstruktur.  Das bedeutet, dass Lichtquellen für jede Farbe gleichmäßig über den Pixelbereich verteilt werden. Dies wird auch als Graustufenrendering bezeichnet.  Auf diese Weise arbeitet ein Standardanzeigegerät.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] wird nie auf den gerenderten Text angewendet.|  
|RGB|1|Das Anzeigegerät hat Pixel, die aus drei Streifen in der folgenden Reihenfolge bestehen: Rot, Grün und Blau.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] wird auf den gerenderten Text angewendet.|  
|BGR|2|Das Anzeigegerät hat Pixel, die aus drei Streifen in der folgenden Reihenfolge bestehen: Blau, Grün und Rot.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] wird auf den gerenderten Text angewendet.  Beachten Sie, wie die Reihenfolge verglichen mit dem RGB\-Typ umgekehrt wird.|  
  
 Die Pixelstruktur entspricht einem Ganzzahlenwert im Bereich zwischen 0 und 2.  Die Standardeinstellung ist 0, d. h. eine flache Pixelstruktur.  
  
> [!NOTE]
>  Informationen zur Auflistung von Anzeigegerätenamen finden Sie unter der `EnumDisplayDevices`\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Funktion.  
  
### Registrierungseinstellung  
 Die Registrierungseinstellung für die Pixelstruktur ist eine lokale Computereinstellung, die einem bestimmten Anzeigegerätenamen entspricht:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für einen Benutzer wird ein `PixelStructure`\-DWORD\-Wert definiert.  Die folgende Bildschirmabbildung zeigt die Registrierungs\-Editor\-Einstellung für die Pixelstruktur.  
  
 ![ClearType&#45;Einstellungen im Registrierungs&#45;Editor](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="text_contrast_level"></a>   
## Textkontraststufe  
 Die Textkontraststufe ermöglicht, das Textrendering auf der Basis des Farbempfindens und der Strichstärken von Symbolen anzupassen.  Die Textkontraststufe ist ein Ganzzahlenwert im Bereich zwischen 0 und 6 \(je größer der Ganzzahlenwert, desto breiter die Strichstärke\).  Der Standardwert ist 1.  
  
### Registrierungseinstellung  
 Die Registrierungseinstellung für die Textkontraststufe wird in einer individuellen Benutzereinstellung platziert, die einem bestimmten Anzeigegerätenamen entspricht:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für einen Benutzer wird ein `TextContrastLevel`\-DWORD\-Wert definiert.  Die folgende Bildschirmabbildung zeigt die Registrierungs\-Editor\-Einstellung für die Textkontraststufe.  
  
 ![ClearType&#45;Einstellungen im Registrierungs&#45;Editor](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
## Siehe auch  
 [Übersicht über ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)   
 [ClearType\-Antialiasing](_win32_ClearType_Antialiasing)