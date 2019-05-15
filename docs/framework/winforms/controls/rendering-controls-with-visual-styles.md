---
title: Rendering von Steuerelementen mit visuellen Stilen
ms.date: 03/30/2017
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- themes [Windows Forms], XP visual styles in Window Forms
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- visual themes [Windows Forms], rendering Windows Forms controls
- user controls [Windows Forms], painting
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a5b178ba-610e-46c4-a6c0-509c0886a744
ms.openlocfilehash: 4dbccfc881e777309394aed9711a93b8a25315be
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592608"
---
# <a name="rendering-controls-with-visual-styles"></a>Rendering von Steuerelementen mit visuellen Stilen
.NET Framework bietet Unterstützung für das Rendern von Steuerelementen und anderen Windows-Benutzer Elemente der Benutzeroberfläche (UI), die mithilfe visueller Stile in Betriebssystemen, die sie unterstützen. In diesem Thema erläutert die verschiedenen Arten der Unterstützung in .NET Framework für das Rendern von Steuerelementen und anderen UI-Elementen mit dem aktuellen visuellen Stil des Betriebssystems.  
  
## <a name="rendering-classes-for-common-controls"></a>Rendern von Klassen für allgemeine Steuerelemente  
 Unter dem Rendern eine Steuerelements versteht man das Zeichnen der Benutzeroberfläche eines Steuerelements. Der <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace stellt die <xref:System.Windows.Forms.ControlPaint> -Klasse zum Rendern einiger allgemeiner Windows Forms-Steuerelemente bereit. Allerdings zeichnet diese Klasse die Steuerelemente im klassischen Windows-Stil. Dies kann eine einheitliche Gestaltung der Benutzeroberfläche erschweren, wenn das Zeichnen benutzerdefinierter Steuerelemente in Anwendungen mit visuellen Stilen aktiviert ist.  
  
 Das [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] beinhaltet Klassen im <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace, die Teile und Zustände von allgemeinen Steuerelementen mit visuellen Stilen rendern. Jede dieser Klassen enthält `static` -Methoden für das Zeichnen des Steuerelements oder Teile des Steuerelements in einem bestimmten Zustand mit dem aktuellen visuellen Stil des Betriebssystems.  
  
 Einige dieser Klassen dienen dem Zeichnen des zugehörigen Steuerelements, unabhängig davon, ob visuelle Stile verfügbar sind. Wenn visuelle Stile aktiviert sind, werden die Klassenelemente das zugehörige Steuerelement mit visuellen Stilen gezeichnet. Wenn visuelle Stile deaktiviert sind, zeichnen die Klassenelemente das Steuerelement im klassischen Windows-Stil. Diese Klassen umfassen:  
  
- <xref:System.Windows.Forms.ButtonRenderer>  
  
- <xref:System.Windows.Forms.CheckBoxRenderer>  
  
- <xref:System.Windows.Forms.GroupBoxRenderer>  
  
- <xref:System.Windows.Forms.RadioButtonRenderer>  
  
 Andere Klassen können das zugehörige Steuerelement nur zeichnen, wenn visuelle Stile verfügbar sind, und ihre Member löst eine Ausnahme aus, wenn visuelle Stile deaktiviert sind. Diese Klassen umfassen:  
  
- <xref:System.Windows.Forms.ComboBoxRenderer>  
  
- <xref:System.Windows.Forms.ProgressBarRenderer>  
  
- <xref:System.Windows.Forms.ScrollBarRenderer>  
  
- <xref:System.Windows.Forms.TabRenderer>  
  
- <xref:System.Windows.Forms.TextBoxRenderer>  
  
- <xref:System.Windows.Forms.TrackBarRenderer>  
  
 Weitere Informationen zum Verwenden dieser Klassen zum Zeichnen eines Steuerelements finden Sie unter [Vorgehensweise: Verwenden eine Steuerelementwiedergabeklasse](how-to-use-a-control-rendering-class.md).  
  
## <a name="visual-style-element-and-rendering-classes"></a>Visuelles Stilelement und Renderingklassen  
 Der <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> -Namespace enthält Klassen, die zum Zeichnen und Abrufen von Informationen über jedes Steuerelement oder UI-Element verwendet werden können, das von visuellen Stilen unterstützt wird. Unterstützte Steuerelemente enthalten allgemeine Steuerelemente, die über eine Rendering-Klasse im <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace verfügen (s. Abschnitt oben), sowie andere Steuerelemente, z.B. Registersteuerelemente und Grundleistensteuerelemente. Weitere unterstützte UI-Elemente sind z.B. Teile des **Startmenüs** , der Taskleiste und des Nicht-Clientbereichs von Windows.  
  
 Die wichtigsten Klassen des <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> -Namespaces sind <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> und <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>. <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> ist eine Foundation Class zur Ermittlung aller von visuellen Stilen unterstützten Steuerelemente oder Benutzeroberflächenelemente. Zusätzlich zu <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> selbst enthält der <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> -Namespace viele geschachtelte Klassen von <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> mit `static` -Eigenschaften, die <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> für jeden Zustand eines Steuerelements, Teil eines Steuerelements oder jedes UI-Element zurückgeben, der bzw. das von visuellen Stilen unterstützt wird.  
  
 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> stellt Methoden zum Zeichnen und Abrufen von Informationen zu jedem einzelnen <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> bereit, das durch den aktuellen visuellen Stil des Betriebssystems definiert wird. Die Informationen, die über ein Element abgerufen werden können, beinhalten die Standardgröße, den Hintergrundtyp und die Farbdefinitionen. <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> umschließt die Funktionalität der API für visuelle Stile (UxTheme) aus dem Windows Shell-Bereich der Windows Platform SDK. Weitere Informationen finden Sie unter [Aktivieren von visuellen Stilen](/windows/desktop/controls/cookbook-overview).  
  
 Weitere Informationen zur Verwendung von <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> und <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, finden Sie unter [Vorgehensweise: Rendern eines visuellen Stilelements](how-to-render-a-visual-style-element.md).  
  
## <a name="enabling-visual-styles"></a>Aktivieren von visuellen Stilen  
 Um visuelle Stile für eine Anwendung, die für .NET Framework, Version 1.0 geschrieben zu aktivieren, müssen Programmierer ein Anwendungsmanifest hinzufügen, der angibt, dass ComCtl32.dll Version 6 oder höher zum Zeichnen von Steuerelementen verwendet werden soll. Anwendungen, die mit .NET Framework, Version 1.1 oder höher können die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode der <xref:System.Windows.Forms.Application> Klasse.  
  
## <a name="checking-for-visual-styles-support"></a>Überprüfen der Unterstützung für visuelle Stile  
 Die <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> -Eigenschaft der <xref:System.Windows.Forms.Application> -Klasse gibt an, ob die aktuelle Anwendung Steuerelemente mit visuellen Stilen zeichnet. Wenn Sie ein benutzerdefiniertes Steuerelement zeichnen, können Sie den Wert von <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> anzeigen, um zu festzulegen, ob das Steuerelement mit oder ohne visuelle Stile gerendert werden soll. In der folgenden Tabelle werden die vier Faktoren aufgelistet, die gegeben sein müssen, damit <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> `true`zurückgibt.  
  
|Bedingung|Hinweise|  
|---------------|-----------|  
|Das Betriebssystem unterstützt visuelle Stile.|Verwenden Sie die <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsSupportedByOS%2A> -Eigenschaft der <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> -Klasse, um diese Bedingung separat zu überprüfen.|  
|Der Benutzer hat visuelle Stile auf seinem Betriebssystem aktiviert.|Verwenden Sie die <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsEnabledByUser%2A> -Eigenschaft der <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> -Klasse, um diese Bedingung separat zu überprüfen.|  
|Visuelle Stile sind in der Anwendung aktiviert.|Visuelle Stile können in einer Anwendung durch Aufrufen der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> -Methode oder mithilfe des Anwendungsmanifests aktiviert werden. Das Manifest gibt an, dass Version 6 von „ComCtl32.dll“ oder höher zum Zeichnen von Steuerelementen verwendet werden wird.|  
|Visuelle Stile werden dazu verwendet, den Clientbereich von Anwendungsfenstern zu zeichnen.|Verwenden Sie die <xref:System.Windows.Forms.Application.VisualStyleState%2A> -Eigenschaft der <xref:System.Windows.Forms.Application> -Klasse und überprüfen Sie, ob sie den Wert <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAreaEnabled?displayProperty=nameWithType> oder <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAndNonClientAreasEnabled?displayProperty=nameWithType>aufweist, um diese Bedingung separat zu überprüfen.|  
  
 Überprüfen Sie den <xref:Microsoft.Win32.UserPreferenceCategory.VisualStyle?displayProperty=nameWithType> -Wert in den Handlern auf <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging?displayProperty=nameWithType> - oder <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged?displayProperty=nameWithType> -Ereignisse, um zu ermitteln, ob Benutzer visuelle Stile aktiviert oder deaktiviert haben oder ob sie von einem visuellen Stil zu einem anderen gewechselt haben.  
  
> [!IMPORTANT]
>  Wenn Sie <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> verwenden möchten, um ein Steuerelement oder ein UI-Element zu rendern, müssen Sie, wenn der Benutzer visuelle Stile aktiviert oder zwischen ihnen wechselt, sicherstellen, dass Sie dies während der Verarbeitung des <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignisses und nicht während der Verarbeitung des <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging> -Ereignisses tun. Eine Ausnahme wird ausgelöst, wenn Sie mithilfe der <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> -Klasse bei der Verarbeitung von <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging>verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Zeichnen und Rendern von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md)
