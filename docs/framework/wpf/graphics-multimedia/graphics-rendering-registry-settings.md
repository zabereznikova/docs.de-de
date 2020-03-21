---
title: Registrierungseinstellungen für das Rendern von Grafiken
ms.date: 03/30/2017
helpviewer_keywords:
- rendering graphics [WPF], registry settings
- rendering graphics [WPF]
- rendering graphics [WPF], troubleshooting
- troubleshooting graphics rendering [WPF]
- graphics [WPF], rendering
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
ms.openlocfilehash: 642dfdd784af4b85672cf5b0c8e60079763f4c47
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112283"
---
# <a name="graphics-rendering-registry-settings"></a>Registrierungseinstellungen für das Rendern von Grafiken
Dieses Thema bietet eine Übersicht über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Registrierungseinstellungen für das Rendern von Grafiken, die sich auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen auswirken.  

<a name="overview"></a>
## <a name="when-to-use-graphics-rendering-registry-settings"></a>Verwenden von Registrierungseinstellungen für das Rendern von Grafiken  
 Diese Registrierungseinstellungen werden für die Problembehandlung, das Debuggen und Produktsupportzwecke bereitgestellt. Da sich Änderungen an der Registrierung auf alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen auswirken, darf Ihre Anwendung diese Registrierungsschlüssel niemals automatisch oder während der Installation ändern.  
  
<a name="xpdmandwddm"></a>
## <a name="what-are-xpdm-and-wddm"></a>Was sind XPDM und WDDM?  
 Einige der Registrierungseinstellungen für das Rendern von Grafiken besitzen unterschiedliche Werte, je nachdem, ob Ihre Grafikkarte einen XPDM- oder einen WDDM-Treiber verwendet. XPDM ist das Microsoft Windows XP Display Driver Model und WDDM ist das Windows Display Driver Model. WDDM ist auf Computern mit Windows Vista und Windows 7 verfügbar. XPDM ist auf Computern mit Windows Vista, Microsoft Windows XP und Microsoft Windows Server 2003 verfügbar. Weitere Informationen zu WDDM finden Sie unter [Windows Display Driver Model (WDDM) Design Guide](/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide).  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>Registrierungseinstellungen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet vier Registrierungseinstellungen zum Steuern des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Renderings:  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|**Option zum Deaktivieren der Hardwarebeschleunigung**|Gibt an, ob die Hardwarebeschleunigung aktiviert werden soll|  
|**Maximaler Wert für Multisampling**|Gibt den Grad des Multisamplings für das Antialiasing von 3D-Inhalten an.|  
|**Einstellung für das erforderliche Videotreiberdatum**|Gibt an, ob das System die Hardwarebeschleunigung für Treiber deaktiviert, die vor November 2004 veröffentlicht wurden|  
|**Option zum Verwenden des Referenzrasters**|Gibt an, ob [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Referenzraster verwendet werden soll|  
  
 Diese Einstellungen stehen für alle externen Konfigurationshilfsprogramme zur Verfügung, die auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Registrierungseinstellungen verweisen können. Diese Einstellungen können auch erstellt oder geändert werden, indem Sie direkt über den Windows-Registrierungs-Editor auf die Werte zugreifen.  
  
<a name="disablehardwareacceleration"></a>
## <a name="disable-hardware-acceleration-option"></a>Option zum Deaktivieren der Hardwarebeschleunigung  
  
|Registrierungsschlüssel|Werttyp|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|DWORD|  
  
 Mit der **Option zum Deaktivieren der Hardwarebeschleunigung** können Sie die Hardwarebeschleunigung beim Debuggen und Testen deaktivieren. Wenn Renderingartefakte in einer Anwendung angezeigt werden, versuchen Sie die Hardwarebeschleunigung zu deaktivieren. Wenn das Artefakt verschwindet, kann es sich um ein Problem mit Ihrem Videotreiber handeln.  
  
 Die **Option zum Deaktivieren der Hardwarebeschleunigung** ist ein DWORD-Wert, der entweder 0 oder 1 ist. Der Wert 1 deaktiviert die Hardwarebeschleunigung. Mit dem Wert 0 wird die Hardwarebeschleunigung aktiviert, sofern das System die entsprechenden Anforderungen erfüllt. Weitere Informationen finden Sie unter [Renderingebenen für Grafiken](../advanced/graphics-rendering-tiers.md).  
  
<a name="maxmultisample"></a>
## <a name="maximum-multisample-value"></a>Maximaler Wert für Multisampling  
  
|Registrierungsschlüssel|Werttyp|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|DWORD|  
  
 Mit dem **maximalen Multisample-Wert** können Sie die maximale Antialiasing-Menge von 3D-Inhalten anpassen. Verwenden Sie diese Ebene, um 3D-Antialiasing in Windows Vista zu deaktivieren.  
  
 Der **maximale Wert für Multisampling** ist ein DWORD-Wert, der zwischen 0 und 16 liegt. Der Wert 0 gibt an, dass das Multisample-Antialiasing von 3D-Inhalten deaktiviert werden soll, und ein Wert von 16 versucht, bis zu 16x Multisample-Antialiasing zu verwenden, wenn es von der Grafikkarte unterstützt wird. Beachten Sie, dass das Festlegen dieses Registrierungsschlüsselwerts auf Computern mit XPDM-Treibern dazu führt, dass Anwendungen eine große Menge an zusätzlichem Videospeicher verwenden, die Leistung des 3D-Renderings beeinträchtigen und Renderingfehler und Stabilität verursachen können. Probleme.  
  
 Wenn dieser Registrierungsschlüssel nicht festgelegt ist, wird [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für XPDM-Treiber auf den Standardwert 0 und für WDDM-Treiber auf den Standardwert 4 gesetzt.  
  
<a name="requiredvideodriverdatesetting"></a>
## <a name="required-video-driver-date-setting"></a>Einstellung des erforderlichen Videotreiberdatums  
  
|Registrierungsschlüssel|Werttyp|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|String|  
  
 Im November 2004 veröffentlichte Microsoft eine neue Version der Treibertestrichtlinien. die nach diesem Datum geschriebenen Treiber bieten eine bessere Stabilität. In der Standardeinstellung nutzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Hardwarebeschleunigungspipeline für diese Treiber und greift bei vor diesem Datum veröffentlichten XPDM-Treibern auf Softwarerendering zurück.  
  
 Die **Einstellung für das erforderliche Videotreiberdatum** ermöglicht es Ihnen, einen alternativen minimalen Datumswert für XPDM-Treiber anzugeben. Ein Datum vor November 2004 sollten Sie nur dann angeben, wenn Sie sicher sind, dass Ihr Videotreiber stabil genug für die Unterstützung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist.  
  
 Für die erforderliche Einstellung für den Videotreiber wird eine Zeichenfolge im folgenden Format verwendet:  
  
| |  
|-|  
|*YYYY* `/` *MM* `/` *DD*|  
  
 Hierbei steht *JJJJ* für das Jahr (vierstellig), *MM* für den Monat (zweistellig) und *TT* für den Tag (zweistellig). Wenn dieser Wert nicht festgelegt ist, verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] November 2004 als erforderliches Datum.  
  
<a name="usereferencerasterizeroption"></a>
## <a name="use-reference-rasterizer-option"></a>Option zum Verwenden des Referenzrasters  
  
|Registrierungsschlüssel|Werttyp|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|DWORD|  
  
 Mit der **Option Referenz-Rasterizer verwenden** können Sie den simulierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hardware-Rendering-Modus zum Debuggen erzwingen: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wechselt in den Hardwaremodus, verwendet jedoch den Microsoft Direct3D-Referenzsoftware-Rasterizer d3dref9.dll anstelle eines tatsächlichen Hardwaregeräts.  
  
 Das Referenzraster ist sehr langsam, umgeht aber Ihren Videotreiber, wodurch durch Treiberprobleme verursachte Renderingprobleme vermieden werden. Aus diesem Grund können Sie das Referenzraster verwenden, um zu ermitteln, ob Renderingprobleme vom Videotreiber verursacht werden. Die Datei „d3dref9.dll“ muss sich an einem Speicherort befinden, auf den die Anwendung zugreifen kann, z.B. an einem beliebigen Speicherort im Systempfad oder im lokalen Verzeichnis der Anwendung.  
  
 Die **Option zum Verwenden des Referenzrasters** verwendet einen DWORD-Wert. Der Wert 0 gibt an, dass das Referenzraster nicht verwendet wird. Jeder Wert ungleich 0 (null) erzwingt, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Referenzraster verwendet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Renderingebenen für Grafiken](../advanced/graphics-rendering-tiers.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
