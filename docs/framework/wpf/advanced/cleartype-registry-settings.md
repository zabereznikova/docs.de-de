---
title: ClearType-Registrierungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: a776c3d4060b9ca291e4e919ab6ca33fb713434c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051393"
---
# <a name="cleartype-registry-settings"></a>ClearType-Registrierungseinstellungen
Dieses Thema enthält eine Übersicht über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] registrierungseinstellungen, mit denen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen.  

<a name="overview"></a>   
## <a name="technology-overview"></a>Übersicht über die Technologie  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, Rendern von Text, der einer Anzeige verwenden [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Funktionen, um eine bessere Lesbarkeit zu gewährleisten. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] ist eine von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] entwickelte Softwaretechnologie, mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), z.B. auf Laptopbildschirmen, Pocket PC-Bildschirmen und Flachbildschirmen, optimiert wird. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] greift dabei auf die einzelnen vertikalen Farbstreifenelemente in jedem Pixel auf einem LCD-Bildschirm zu. Weitere Informationen zu [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], finden Sie unter [Übersicht über ClearType](cleartype-overview.md).  
  
 Mit gerenderter Text [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] deutlich unterschiedlich auf verschiedenen Anzeigegeräten angezeigt werden können. Implementieren beispielsweise eine kleine Anzahl von Monitoren die Farbstreifenelemente in Blau, Grün, Rot Reihenfolge anstelle der häufiger Rot, Grün, Blau ( [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) Reihenfolge.  
  
 Mit gerenderter Text [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] stehen auch deutlich unterschiedlich von Personen mit unterschiedlicher farbempfindlichkeit angezeigt. Manche Benutzer erkennen leichte Farbunterschiede besser als andere.  
  
 In allen diesen Fällen [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Funktionen geändert werden müssen, um die optimale Lesbarkeit für jede Einzelperson bereitzustellen.  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Registrierungseinstellungen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt vier registrierungseinstellungen zum Steuern der [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Features:  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Ebene|Beschreibt den Grad der [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] farbklarheit.|  
|Gammastufe|Beschreibt die Ebene der Pixelfarbkomponente für ein Anzeigegerät.|  
|Pixelstruktur|Beschreibt die Anordnung der Pixel für ein Anzeigegerät.|  
|Textkontrastebene|Beschreibt die Kontrastebene für den angezeigten Text.|  
  
 Diese Einstellungen können von einem externen Konfigurationsprogramm aus, das die angegebene verweisen kann, zugegriffen werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] registrierungseinstellungen. Diese Einstellungen können auch erstellt oder geändert werden, indem Sie direkt über den [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Registrierungs-Editor auf die Werte zugreifen.  
  
 Wenn die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] registrierungseinstellungen sind nicht festgelegt (Standardzustand ist), die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungsabfragen der [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] -systemparameterinformationen für die Einstellungen für die schriftartglättung.  
  
> [!NOTE]
>  Informationen über das Auflisten von Anzeigegerätenamen finden Sie in der `SystemParametersInfo` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion.  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>ClearType-Ebene  
 Die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Ebene können Sie das Rendern von Text auf Basis der farbempfindlichkeit und Wahrnehmung einer Person anpassen. Für einige Benutzer das Rendern von Text, verwendet [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] auf der höchsten Ebene erzeugt keinen die optimale Lesbarkeit.  
  
 Die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Ebene ist ein ganzzahliger Wert, der zwischen 0 und 100 liegt. Der Standardwert ist 100, d. h. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] verwendet die maximale Funktion der Farbstreifenelemente des Anzeigegeräts. Allerdings eine [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Ebene 0 Text, Graustufen gerendert. Durch Festlegen der [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] auf einen Wert zwischen 0 und 100 liegen, können Sie erstellen einen mittleren Wissensstand, die für eine individuelle farbempfindlichkeit geeignet ist.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort der Einstellung für die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Ebene ist eine lokale benutzereinstellung, die einem bestimmten Anzeigegerätenamen entspricht:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen eines Benutzers einer `ClearTypeLevel` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Ebene.  
  
 ![ClearType-Einstellungen im Registrierungs-Editor.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungen Rendern Text in einem der beiden Modi: mit und ohne [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]. Wenn Text gerendert wird, ohne [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], wird dies als Graustufenrendering bezeichnet.  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>Gammastufe  
 Die Gammastufe bezieht sich auf die nicht lineare Beziehung zwischen einem Pixelwert und der Leuchtdichte. Die Einstellung der Gammastufe muss mit den physischen Eigenschaften des Anzeigegeräts übereinstimmen. Andernfalls wird die gerenderte Ausgabe möglicherweise verzerrt dargestellt. So kann der Text beispielsweise zu breit oder zu schmal angezeigt werden, oder es treten Farbränder an vertikalen Symbolstrichen auf.  
  
 Die Gammastufe ist ein Ganzzahlwert zwischen 1000 und 2200. Der Standardwert ist 1900.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Gammastufe ist eine lokale Computereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen eines Benutzers einer `GammaLevel` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Gammastufe.  
  
 ![ClearType-Gamma auf Einstellungen im Registrierungs-Editor](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>Pixelstruktur  
 Die Pixelstruktur beschreibt den Pixeltyp, aus dem ein Anzeigegerät besteht. Die Pixelstruktur ist definiert als eine der folgenden drei Typen:  
  
|Typ|Wert|Beschreibung|  
|----------|-----------|-----------------|  
|Flach|0|Das Anzeigegerät hat keine Pixelstruktur. Das bedeutet, dass Lichtquellen für jede Farbe gleichmäßig über den Pixelbereich verteilt werden, was auch als Graustufenrendering bezeichnet wird. Auf diese Weise funktioniert ein Standardanzeigegerät. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] wird nie auf den gerenderten Text angewendet.|  
|RGB|1|Das Anzeigegerät hat Pixel, die aus drei Farbstreifen in der folgenden Reihenfolge bestehen: Rot, Grün und Blau. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] wird auf den gerenderten Text angewendet.|  
|BGR|2|Das Anzeigegerät hat Pixel, die aus drei Farbstreifen in der folgenden Reihenfolge bestehen: Blau, Grün und Rot. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] wird auf den gerenderten Text angewendet. Beachten Sie, wie hier die Reihenfolge des RGB-Typs umgekehrt wird.|  
  
 Die Pixelstruktur entspricht einem Ganzzahlwert zwischen 0 und 2. Der Standardwert ist 0, was einer flachen Pixelstruktur entspricht.  
  
> [!NOTE]
>  Informationen über das Auflisten von Anzeigegerätenamen finden Sie in der `EnumDisplayDevices` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Pixelstruktur ist eine lokale Computereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen eines Benutzers einer `PixelStructure` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Pixelstruktur.  
  
 ![ClearType-Gamma auf Einstellungen im Registrierungs-Editor](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>Textkontraststufe  
 Mithilfe der Textkontraststufe können Sie das Textrendering an die Strichstärke von Symbolen anpassen. Die Textkontraststufe ist ein Ganzzahlwert zwischen 0 und 6. Hierbei gilt: Je größer der Wert, desto breiter die Strichstärke. Der Standardwert ist 1.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Textkontraststufe ist eine lokale Benutzereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegerätenamen eines Benutzers einer `TextContrastLevel` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Textkontraststufe.  
  
 ![ClearType-Einstellungen im Registrierungs-Editor.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ClearType](cleartype-overview.md)
- [ClearType-Antialiasing](/windows/desktop/gdi/cleartype-antialiasing)
