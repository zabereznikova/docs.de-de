---
title: ClearType-Registrierungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 6143cf835cc44a6c6cc50372b2ac1a4d24d65311
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740380"
---
# <a name="cleartype-registry-settings"></a>ClearType-Registrierungseinstellungen
Dieses Thema enthält eine Übersicht über die Microsoft ClearType-Registrierungs Einstellungen, die von WPF-Anwendungen verwendet werden.  

<a name="overview"></a>   
## <a name="technology-overview"></a>Übersicht über die Technologie  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, die Text auf einem Anzeigegerät darstellen, verwenden ClearType-Funktionen, um ein verbessertes Leseverhalten bereitzustellen. ClearType ist eine von Microsoft entwickelte Softwaretechnologie, mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), wie z. b. Laptop Bildschirmen, Pocket PC-Bildschirme und Flatpanel-Monitoren, verbessert wird. ClearType funktioniert, indem auf die einzelnen vertikalen Farbstreifen Elemente in jedem Pixel eines LCD-Bildschirms zugegriffen wird. Weitere Informationen zu ClearType finden Sie unter [Übersicht über ClearType](cleartype-overview.md).  
  
 Text, der mit ClearType gerendert wird, kann bei Anzeige auf verschiedenen Anzeigegeräten erheblich anders erscheinen. Eine kleine Anzahl von Monitoren implementiert beispielsweise die Farbstreifen Elemente in der blauen, grünen und roten Reihenfolge anstelle der gängigeren roten, grünen und blauen Reihenfolge (RGB).  
  
 Text, der mit ClearType gerendert wird, kann sich auch erheblich unterscheiden, wenn er von Einzelpersonen mit unterschiedlichen Farb Sensitivität angezeigt wird. Manche Benutzer erkennen leichte Farbunterschiede besser als andere.  
  
 In jedem dieser Fälle müssen ClearType-Features geändert werden, um für jede Einzelperson das beste Leseverhalten bereitzustellen.  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Registrierungseinstellungen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt vier Registrierungs Einstellungen zum Steuern von ClearType-Features an:  
  
|-Einstellung|Beschreibung|  
|-------------|-----------------|  
|ClearType-Ebene|Beschreibt die Ebene der ClearType-Farb Übersichtlichkeit.|  
|Gammastufe|Beschreibt die Ebene der Pixelfarbkomponente für ein Anzeigegerät.|  
|Pixelstruktur|Beschreibt die Anordnung der Pixel für ein Anzeigegerät.|  
|Textkontrastebene|Beschreibt die Kontrastebene für den angezeigten Text.|  
  
 Auf diese Einstellungen kann von einem externen Konfigurations Hilfsprogramm zugegriffen werden, das auf die identifizierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-ClearType-Registrierungs Einstellungen verweist. Diese Einstellungen können auch erstellt oder geändert werden, indem Sie direkt über den Windows-Registrierungs-Editor auf die Werte zugreifen.  
  
 Wenn die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType-Registrierungs Einstellungen nicht festgelegt sind (Dies ist der Standardzustand), fragt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung die Windows-Systemparameter Informationen für die Einstellungen der Schriftart Glättung ab.  
  
> [!NOTE]
> Weitere Informationen zum Auflisten von Anzeigegeräte Namen finden Sie in der `SystemParametersInfo`Win32-Funktion.  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>ClearType-Ebene  
 Mit der ClearType-Ebene können Sie das Rendering von Text basierend auf der Farb Sensitivität und der Wahrnehmung einer einzelnen Person anpassen. Für einige Benutzer erzeugt das Rendering von Text, der ClearType auf der höchsten Ebene verwendet, nicht die beste Lese Umgebung.  
  
 Die ClearType-Ebene ist ein ganzzahliger Wert zwischen 0 und 100. Die Standard Ebene ist 100, was bedeutet, dass ClearType die maximale Funktion der Farbstreifen Elemente des Anzeige Geräts verwendet. Allerdings rendert die ClearType-Ebene 0 den Text als graue Skala. Durch Festlegen der ClearType-Ebene irgendwo zwischen 0 und 100 können Sie eine Zwischenebene erstellen, die für die Farb Sensitivität einer einzelnen Person geeignet ist.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Speicherort der Registrierungs Einstellung für die ClearType-Ebene ist eine individuelle Benutzereinstellung, die einem bestimmten Anzeigegeräte Namen entspricht:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegeräte Namen eines Benutzers wird ein `ClearTypeLevel` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die ClearType-Ebene.  
  
 ![ClearType-Einstellungen im Registrierungs-Editor.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen RenderText in einem von zwei Modi, mit und ohne ClearType. Wenn Text ohne ClearType gerendert wird, wird er als Graustufen Rendering bezeichnet.  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>Gammastufe  
 Die Gammastufe bezieht sich auf die nicht lineare Beziehung zwischen einem Pixelwert und der Leuchtdichte. Die Einstellung der Gammastufe muss mit den physischen Eigenschaften des Anzeigegeräts übereinstimmen. Andernfalls wird die gerenderte Ausgabe möglicherweise verzerrt dargestellt. Beispielsweise kann Text zu breit oder zu schmal angezeigt werden, oder es können Farbränder an den Rändern vertikaler Symbole angezeigt werden.  
  
 Die Gammastufe ist ein Ganzzahlwert zwischen 1000 und 2200. Der Standardwert ist 1900.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Gammastufe ist eine lokale Computereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegeräte Namen eines Benutzers wird ein `GammaLevel` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Gammastufe.  
  
 ![ClearType-Einstellungen der Gamma Ebene im Registrierungs-Editor](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>Pixelstruktur  
 Die Pixelstruktur beschreibt den Pixeltyp, aus dem ein Anzeigegerät besteht. Die Pixelstruktur ist definiert als eine der folgenden drei Typen:  
  
|Typ|{2&gt;Wert&lt;2}|Beschreibung|  
|----------|-----------|-----------------|  
|Flach|0|Das Anzeigegerät hat keine Pixelstruktur. Das bedeutet, dass Lichtquellen für jede Farbe gleichmäßig über den Pixelbereich verteilt werden, was auch als Graustufenrendering bezeichnet wird. Auf diese Weise funktioniert ein Standardanzeigegerät. ClearType wird nie auf den gerenderten Text angewendet.|  
|RGB|1|Das Anzeigegerät hat Pixel, die aus drei Farbstreifen in der folgenden Reihenfolge bestehen: Rot, Grün und Blau. ClearType wird auf den gerenderten Text angewendet.|  
|BGR|2|Das Anzeigegerät hat Pixel, die aus drei Farbstreifen in der folgenden Reihenfolge bestehen: Blau, Grün und Rot. ClearType wird auf den gerenderten Text angewendet. Beachten Sie, wie hier die Reihenfolge des RGB-Typs umgekehrt wird.|  
  
 Die Pixelstruktur entspricht einem Ganzzahlwert zwischen 0 und 2. Der Standardwert ist 0, was einer flachen Pixelstruktur entspricht.  
  
> [!NOTE]
> Weitere Informationen zum Auflisten von Anzeigegeräte Namen finden Sie in der `EnumDisplayDevices`Win32-Funktion.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Pixelstruktur ist eine lokale Computereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegeräte Namen eines Benutzers wird ein `PixelStructure` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Pixelstruktur.  
  
 ![ClearType-Einstellungen der Gamma Ebene im Registrierungs-Editor](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>Textkontraststufe  
 Mithilfe der Textkontraststufe können Sie das Textrendering an die Strichstärke von Symbolen anpassen. Die Textkontraststufe ist ein Ganzzahlwert zwischen 0 und 6. Hierbei gilt: Je größer der Wert, desto breiter die Strichstärke. Der Standardwert ist 1.  
  
### <a name="registry-setting"></a>Registrierungseinstellung  
 Der Ort für die Registrierungseinstellung der Textkontraststufe ist eine lokale Benutzereinstellung und entspricht einem bestimmten Anzeigegerätenamen:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Für jeden Anzeigegeräte Namen eines Benutzers wird ein `TextContrastLevel` DWORD-Wert definiert. Der folgende Screenshot zeigt die Registrierungs-Editor-Einstellung für die Textkontraststufe.  
  
 ![ClearType-Einstellungen im Registrierungs-Editor.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ClearType](cleartype-overview.md)
- [ClearType-Antialiasing](/windows/desktop/gdi/cleartype-antialiasing)
