---
title: Zusammenführen von Menüelementen im MenuStrip-Steuerelement von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: dbe1c0325499e7b925d504fc80f9034f9e387475
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231564"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Zusammenführen von Menüelementen im MenuStrip-Steuerelement von Windows Forms
Wenn Sie eine Anwendung für die Multiple Document Interface (MDI) verfügen, können Sie Menüelemente oder ganze Menüs aus dem untergeordnete Formular in den Menüs des übergeordneten Formulars zusammenführen.  
  
 Dieses Thema beschreibt die grundlegenden Konzepte, Zusammenführen von Menüelementen in einer MDI-Anwendung zugeordnet.  
  
## <a name="general-concepts"></a>Allgemeine Konzepte  
 Das Zusammenführen von Prozeduren umfassen sowohl ein Ziel und ein Datenquellen-Steuerelement:  
  
-   Das Ziel ist die <xref:System.Windows.Forms.MenuStrip> Steuerelement im Hauptformular oder das übergeordnete MDI-Formular, in dem Sie Menüelemente zusammengeführt werden.  
  
-   Die Quelle ist die <xref:System.Windows.Forms.MenuStrip> Steuerelement die untergeordneten MDI-Formulars, das die Menüelemente enthält, in dem Menü "Ziel" zusammenzuführen.  
  
 Die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> identifiziert das Menüelement, deren Dropdown-Listenfeld, füllen Sie die Titel der aktuellen MDI, übergeordnete Formular des untergeordneten MDI-Objekte. Angenommen, Sie untergeordnete MDI-Fenster, die derzeit geöffnet sind in der Regel Auflisten der **Fenster** Menü.  
  
 Die <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> Eigenschaft identifiziert, welche die Menüelemente stammen eine <xref:System.Windows.Forms.MenuStrip> auf ein untergeordnetes MDI-Formular.  
  
 Sie können Menüelemente manuell oder automatisch zusammenführen. Die Menüelemente zusammenzuführen, auf die gleiche Weise bei beiden Methoden, aber die Zusammenführung ist anders, wie in den Abschnitten "Manuell zusammenführen" und "Automatische Zusammenführung wird durch" weiter unten in diesem Thema erläutert aktiviert. Manueller und automatischer zusammengeführt, jeder Zusammenführungsvorgang wirkt sich auf die nächste Aktion für die Mergereplikation.  
  
 <xref:System.Windows.Forms.MenuStrip> Zusammenführen von Menüelementen aus einem verschiebt <xref:System.Windows.Forms.ToolStrip> in ein anderes anstatt zu klonen, wie bei der Fall war <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>MergeAction-Werte  
 Festlegen der Merge-Aktion auf Menüelemente in der Quelle <xref:System.Windows.Forms.MenuStrip> mithilfe der <xref:System.Windows.Forms.MergeAction> Eigenschaft.  
  
 Die folgende Tabelle beschreibt die Bedeutung und die typische Verwendung der verfügbaren Merge Aktionen.  
  
|MergeAction-Wert|Beschreibung|Typische Verwendung|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(Standard) Hinzugefügt am Ende der Auflistung für das Zielelement das Quellelement zu.|Hinzufügen von Menüelementen an das Ende des Menüs, wenn ein Teil des Programms aktiviert ist.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Fügt das Quellelement das Zielelement-Auflistung, an dem vom angegebenen Speicherort der <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Eigenschaft festgelegt wird, auf das Quellelement.|Hinzufügen von Menüelementen in die Mitte oder am Anfang des Menüs ein, wenn ein Teil des Programms aktiviert ist.<br /><br /> Wenn der Wert des <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> ist identisch für beide Menüelemente werden sie hinzugefügt, in umgekehrter Reihenfolge. Legen Sie <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> entsprechend um die ursprüngliche Reihenfolge beizubehalten.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Findet eine Übereinstimmung von Text oder verwendet den <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Wert, wenn keine Übereinstimmung von Text gefunden wird, und dann das entsprechende Ziel-Menüelement mit dem Menüelement Quelle ersetzt.|Ersetzen ein Ziel-Menüelement mit einem Menüelement "Source" mit dem gleichen Namen, die etwas anderes ist.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Findet eine Übereinstimmung von Text oder verwendet den <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Wert, wenn keine Übereinstimmung von Text gefunden wird, und dann alle Dropdown-Elemente aus der Quelle zum Ziel fügt.|Erstellen mit einer Menüstruktur, fügt Menüelemente in einem Untermenü hinzugefügt oder entfernt Elemente aus einem Untermenü. Sie können z. B. ein Menüelement eines untergeordneten MDI-hinzufügen, um ein <xref:System.Windows.Forms.MenuStrip> **speichern** Menü.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> können Sie Sie durch die Menüstruktur zu navigieren, ohne dass eine Aktion aus. Es bietet eine Möglichkeit zum Auswerten der nachfolgenden Elemente.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Findet eine Übereinstimmung von Text oder verwendet den <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> -Wert, wenn keine Übereinstimmung von Text gefunden wird, und klicken Sie dann das Element aus der Zieldatenbank entfernt.|Entfernen ein Menüelement aus dem Ziel <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Manuelles Zusammenführen  
 Nur <xref:System.Windows.Forms.MenuStrip> automatische Zusammenführung wird durch Steuerelemente zu teilnehmen. Kombinieren Sie die Elemente von anderen Steuerelementen, z. B. <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.StatusStrip> -Steuerelemente, Sie müssen diese manuell zusammengeführt, durch den Aufruf der <xref:System.Windows.Forms.ToolStripManager.Merge%2A> und <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> Methoden im Code nach Bedarf.  
  
## <a name="automatic-merging"></a>Automatisches zusammenführen  
 Sie können die automatische Zusammenführung für MDI-Anwendungen durch Aktivieren der Quellform verwenden. Verwenden einer <xref:System.Windows.Forms.MenuStrip> legen Sie in einer MDI-Anwendung, die <xref:System.Windows.Forms.Form.MainMenuStrip%2A> die Zieleigenschaft <xref:System.Windows.Forms.MenuStrip> , damit das Zusammenführen von Aktionen für die Datenquelle ausgeführt <xref:System.Windows.Forms.MenuStrip> im Ziel wiedergegeben werden <xref:System.Windows.Forms.MenuStrip>.  
  
 Sie können die automatische Zusammenführung durch Aktivierung Auslösen der <xref:System.Windows.Forms.MenuStrip> der MDI-Quelle. Nach der Aktivierung der Quelle <xref:System.Windows.Forms.MenuStrip> mit dem MDI-Ziel zusammengeführt wird. Wird ein neues Formular aktiv ist, ist die Zusammenführung auf das letzte Formular zurückgesetzt und für das neue Formular ausgelöst. Sie können dieses Verhalten steuern, durch Festlegen der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> Eigenschaft nach Bedarf auf den einzelnen <xref:System.Windows.Forms.ToolStripItem>, und durch Festlegen der <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> Eigenschaft auf den einzelnen <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip-Steuerelement](menustrip-control-windows-forms.md)
- [Vorgehensweise: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Vorgehensweise: Richten Sie automatische Zusammenführen von Menüs für MDI-Anwendungen](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
