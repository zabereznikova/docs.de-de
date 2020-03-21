---
title: ClearType-Registrierungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: bedd99fcf9b4ca1d10b4c24d7cff9de320e6fd12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186173"
---
# <a name="cleartype-registry-settings"></a>ClearType-Registrierungseinstellungen
Dieses Thema bietet einen Überblick über die Microsoft ClearType-Registrierungseinstellungen, die von WPF-Anwendungen verwendet werden.  

<a name="overview"></a>
## <a name="technology-overview"></a>Technologieübersicht  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Anwendungen, die Text auf einem Anzeigegerät rendern, verwenden ClearType-Funktionen, um ein verbessertes Leseerlebnis zu bieten. ClearType ist eine von Microsoft entwickelte Softwaretechnologie, die die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays) wie Laptop-Bildschirmen, Pocket-PC-Bildschirmen und Flachbildschirmen verbessert. ClearType funktioniert, indem es auf die einzelnen vertikalen Farbstreifenelemente in jedem Pixel eines LCD-Bildschirms zugreift. Weitere Informationen zu ClearType finden Sie unter [ClearType Overview](cleartype-overview.md).  
  
 Text, der mit ClearType gerendert wird, kann deutlich anders angezeigt werden, wenn er auf verschiedenen Anzeigegeräten angezeigt wird. Beispielsweise implementiert eine kleine Anzahl von Monitoren die Farbstreifenelemente in blauer, grüner, roter Reihenfolge und nicht in der gebräuchlicheren Roten, Grünen, Blauen (RGB-) Reihenfolge.  
  
 Text, der mit ClearType gerendert wird, kann auch deutlich anders aussehen, wenn er von Personen mit unterschiedlicher Farbempfindlichkeit angezeigt wird. Manche Benutzer erkennen leichte Farbunterschiede besser als andere.  
  
 In jedem dieser Fälle müssen ClearType-Features geändert werden, um die beste Leseerfahrung für jeden Einzelnen zu bieten.  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>Registrierungseinstellungen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gibt vier Registrierungseinstellungen für die Steuerung von ClearType-Features an:  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|ClearType-Ebene|Beschreibt die Ebene der ClearType-Farbklarheit.|  
|Gammastufe|Beschreibt die Ebene der Pixelfarbkomponente für ein Anzeigegerät.|  
|Pixelstruktur|Beschreibt die Anordnung der Pixel für ein Anzeigegerät.|  
|Textkontrastebene|Beschreibt die Kontrastebene für den angezeigten Text.|  
  
 Auf diese Einstellungen kann von einem externen Konfigurationsdienstprogramm [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zugegriffen werden, das weiß, wie auf die identifizierten ClearType-Registrierungseinstellungen verwiesen wird. Diese Einstellungen können auch erstellt oder geändert werden, indem Sie direkt über den Windows-Registrierungs-Editor auf die Werte zugreifen.  
  
 Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die ClearType-Registrierungseinstellungen nicht festgelegt sind (der Standardzustand ist), fragt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung die Windows-Systemparameterinformationen nach Einstellungen für die Schriftartglättung ab.  
  
> [!NOTE]
> Informationen zum Auflisten von Anzeigegerätenamen `SystemParametersInfo`finden Sie in der Win32-Funktion.  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a>ClearType-Ebene  
 Mit der ClearType-Ebene können Sie das Rendern von Text basierend auf der Farbempfindlichkeit und Wahrnehmung einer Person anpassen. Für einige Personen führt das Rendern von Text, der ClearType auf höchster Ebene verwendet, nicht zu den besten Leseerfahrungen.  
  
 Die ClearType-Ebene ist ein ganzzahliger Wert, der zwischen 0 und 100 liegt. Die Standardstufe ist 100, was bedeutet, dass ClearType die maximale Fähigkeit der Farbstreifenelemente des Anzeigegeräts verwendet. Eine ClearType-Ebene von 0 rendert Text jedoch als Graustufen. Wenn Sie die ClearType-Ebene irgendwo zwischen 0 und 100 festlegen, können Sie eine Zwischenebene erstellen, die für die Farbempfindlichkeit einer Person geeignet ist.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Registrierungseinstellungsspeicherort für die ClearType-Ebene ist eine einzelne Benutzereinstellung, die einem bestimmten Anzeigegerätenamen entspricht:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für `ClearTypeLevel` einen Benutzer wird ein DWORD-Wert definiert. Der folgende Screenshot zeigt die Einstellung Registrierungs-Editor für die ClearType-Ebene.  
  
 ![ClearType-Einstellungen im Registrierungs-Editor.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Anwendungen rendern Text in einem der beiden Modi, mit und ohne ClearType. Wenn Text ohne ClearType gerendert wird, wird er als Graustufen-Rendering bezeichnet.  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a>Gammastufe  
 Die Gammastufe bezieht sich auf die nicht lineare Beziehung zwischen einem Pixelwert und der Leuchtdichte. Die Einstellung der Gammastufe muss mit den physischen Eigenschaften des Anzeigegeräts übereinstimmen. Andernfalls wird die gerenderte Ausgabe möglicherweise verzerrt dargestellt. Beispielsweise kann Text zu breit oder zu schmal erscheinen, oder Farbränder erscheinen an den Rändern vertikaler Glyphenstämme.  
  
 Die Gammastufe ist ein Ganzzahlwert zwischen 1000 und 2200. Der Standardwert ist 1900.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Gammastufe ist eine lokale Computereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für `GammaLevel` einen Benutzer wird ein DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Gammastufe.  
  
 ![ClearType-Gammapegeleinstellungen im Registrierungs-Editor](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a>Pixelstruktur  
 Die Pixelstruktur beschreibt den Pixeltyp, aus dem ein Anzeigegerät besteht. Die Pixelstruktur ist definiert als eine der folgenden drei Typen:  
  
|type|value|Beschreibung|  
|----------|-----------|-----------------|  
|Flach|0|Das Anzeigegerät hat keine Pixelstruktur. Das bedeutet, dass Lichtquellen für jede Farbe gleichmäßig über den Pixelbereich verteilt werden, was auch als Graustufenrendering bezeichnet wird. Auf diese Weise funktioniert ein Standardanzeigegerät. ClearType wird nie auf den gerenderten Text angewendet.|  
|RGB|1|Das Anzeigegerät hat Pixel, die aus drei Farbstreifen in der folgenden Reihenfolge bestehen: Rot, Grün und Blau. ClearType wird auf den gerenderten Text angewendet.|  
|BGR|2|Das Anzeigegerät hat Pixel, die aus drei Farbstreifen in der folgenden Reihenfolge bestehen: Blau, Grün und Rot. ClearType wird auf den gerenderten Text angewendet. Beachten Sie, wie hier die Reihenfolge des RGB-Typs umgekehrt wird.|  
  
 Die Pixelstruktur entspricht einem Ganzzahlwert zwischen 0 und 2. Der Standardwert ist 0, was einer flachen Pixelstruktur entspricht.  
  
> [!NOTE]
> Informationen zum Auflisten von Anzeigegerätenamen `EnumDisplayDevices`finden Sie in der Win32-Funktion.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Pixelstruktur ist eine lokale Computereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für `PixelStructure` einen Benutzer wird ein DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Pixelstruktur.  
  
 ![ClearType-Gammapegeleinstellungen im Registrierungs-Editor](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a>Textkontraststufe  
 Mithilfe der Textkontraststufe können Sie das Textrendering an die Strichstärke von Symbolen anpassen. Die Textkontraststufe ist ein Ganzzahlwert zwischen 0 und 6. Hierbei gilt: Je größer der Wert, desto breiter die Strichstärke. Der Standardwert ist 1.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Textkontraststufe ist eine lokale Benutzereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen für `TextContrastLevel` einen Benutzer wird ein DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Textkontraststufe.  
  
 ![ClearType-Einstellungen im Registrierungs-Editor.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ClearType](cleartype-overview.md)
- [ClearType-Antialiasing](/windows/desktop/gdi/cleartype-antialiasing)
