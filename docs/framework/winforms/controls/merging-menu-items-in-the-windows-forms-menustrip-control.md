---
title: "Zusammenführen von Menüelementen im MenuStrip-Steuerelement von Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8e042b3f7b0a2a2e40b8fba33fca6c147086df6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Zusammenführen von Menüelementen im MenuStrip-Steuerelement von Windows Forms
Wenn Sie eine Anwendung Multiple Document Interface (MDI) verfügen, können Sie Menüelemente oder ganze Menüs des untergeordneten Formulars in den Menüs des übergeordneten Formulars zusammenführen.  
  
 Dieses Thema beschreibt die grundlegenden Konzepte, Zusammenführen von Menüelementen in einer MDI-Anwendung zugeordnet.  
  
## <a name="general-concepts"></a>Allgemeine Konzepte  
 Zusammenführen von Prozeduren umfassen ein Ziel und ein Datenquellen-Steuerelement:  
  
-   Das Ziel ist die <xref:System.Windows.Forms.MenuStrip> Steuerelement im Hauptformular oder übergeordneten MDI-Formulars, in dem Sie Menüelemente zusammengeführt werden.  
  
-   Die Quelle ist die <xref:System.Windows.Forms.MenuStrip> Steuerelement untergeordnetes MDI-Formular, das die Menüelemente enthält im Ziel zusammengeführt werden sollen.  
  
 Die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft identifiziert das Menüelement, deren Dropdown-Liste, füllen Sie die Titel der aktuellen MDI, übergeordneten Formulars untergeordnete MDI-Elemente. Angenommen, Sie untergeordnete MDI-Fenster, die derzeit geöffnet sind in der Regel Auflisten der **Fenster** Menü.  
  
 Die <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> Eigenschaft wird angegeben, welche die Menüelemente stammen eine <xref:System.Windows.Forms.MenuStrip> auf ein untergeordnetes MDI-Formular.  
  
 Sie können Menüelemente manuell oder automatisch zusammenführen. Die Menüelemente merge für beide Methoden die gleiche Weise, jedoch die Zusammenführung ist anders, wie in den Abschnitten "Manuell zusammenführen" und "Automatische zusammenführen" weiter unten in diesem Thema erläutert wird aktiviert. Manuelles und automatisches Zusammenführen, jeden Merge-Aktion wirkt sich auf die nächste mergeaktion.  
  
 <xref:System.Windows.Forms.MenuStrip>Zusammenführen von Menüelementen aus einem verschiebt <xref:System.Windows.Forms.ToolStrip> in eine andere statt klonen, wie dies bei der Fall war <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>MergeAction-Werte  
 Setzen Sie die mergeaktion auf Menüelemente in der Quelle <xref:System.Windows.Forms.MenuStrip> mithilfe der <xref:System.Windows.Forms.MergeAction> Eigenschaft.  
  
 Die folgende Tabelle beschreibt die Bedeutung und die typische Verwendung der verfügbaren Merge Aktionen.  
  
|MergeAction-Wert|Beschreibung|Typische Verwendung|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(Standard) Fügt das Quellelement bis zum Ende der Auflistung des Zielelements an.|Hinzufügen von Menüelementen am Ende des Menüs, wenn ein Teil der Anwendung aktiviert wird.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Fügt das Quellelement des Zielelements-Auflistung, in dem durch angegebenen Speicherort der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaft für das Quellelement festgelegt.|Hinzufügen von Menüelementen in der Mitte oder den Anfang des Menüs, wenn ein Teil der Anwendung aktiviert wird.<br /><br /> Wenn der Wert der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> entspricht dem für beide Menüelemente sie in umgekehrter Reihenfolge hinzugefügt werden. Legen Sie <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> entsprechend um die ursprüngliche Reihenfolge beizubehalten.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Findet eine Übereinstimmung Text oder verwendet den <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Wert, wenn keine Übereinstimmung Text gefunden wird, und dann das entsprechende Ziel-Menüelement mit dem Menüelement Quelle ersetzt.|Ersetzen ein Ziel-Menüelement mit einer Quelle Menüelement mit dem gleichen Namen, das etwas anderes durchführt.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Findet eine Übereinstimmung Text oder verwendet den <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Wert, wenn keine Übereinstimmung Text gefunden wird, und dann alle Dropdown-Elemente aus der Quelle zum Ziel fügt.|Erstellen einer Menüstruktur, fügt ein Untermenü Menüelemente fügt oder Menüelemente aus einem Untermenü entfernt. Sie können z. B. ein Menüelement aus untergeordnetes MDI-Fenster hinzufügen, für "Main" eine <xref:System.Windows.Forms.MenuStrip> **speichern unter** Menü.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly>ermöglicht Ihnen die Menüstruktur navigieren, ohne eine Aktion auszuführen. Er bietet eine Möglichkeit zum Auswerten der nachfolgenden Elemente.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Findet eine Übereinstimmung Text oder verwendet den <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Wert, wenn keine Übereinstimmung Text gefunden wird, und klicken Sie dann das Element aus der Zieldatenbank entfernt.|Entfernen eines Menüelements aus dem Ziel <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Manuelles Zusammenführen  
 Nur <xref:System.Windows.Forms.MenuStrip> Steuerelemente automatische Zusammenführen teilnehmen. Kombinieren Sie die Elemente anderer Steuerelemente wie z. B. <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.StatusStrip> Steuerelemente, Sie müssen diese manuell zusammengeführt, durch Aufrufen der <xref:System.Windows.Forms.ToolStripManager.Merge%2A> und <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> Methoden im Code nach Bedarf.  
  
## <a name="automatic-merging"></a>Automatisches zusammenführen  
 Sie können die automatische Zusammenführen für MDI-Anwendungen durch Aktivierung der Source-Format verwenden. Verwenden einer <xref:System.Windows.Forms.MenuStrip> legen Sie in einer MDI-Anwendung, die <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Eigenschaft, um das Ziel <xref:System.Windows.Forms.MenuStrip> , damit das Zusammenführen von Aktionen für die Datenquelle ausgeführt <xref:System.Windows.Forms.MenuStrip> im Ziel wiedergegeben werden <xref:System.Windows.Forms.MenuStrip>.  
  
 Sie können das automatische zusammenführen, indem Sie aktivieren Auslösen der <xref:System.Windows.Forms.MenuStrip> der MDI-Quelle. Nach der Aktivierung der Quelle <xref:System.Windows.Forms.MenuStrip> MDI-Ziel zusammengeführt wird. Wird ein neues Formular aktiv ist, wird die Zusammenführung im letzten Formular zurückgesetzt und auf das neue Formular ausgelöst. Sie können dieses Verhalten steuern, durch Festlegen der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> Eigenschaft nach Bedarf auf jedem <xref:System.Windows.Forms.ToolStripItem>, festlegen und die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> Eigenschaft auf jedem <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 [MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Gewusst wie: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)  
 [Gewusst wie: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
