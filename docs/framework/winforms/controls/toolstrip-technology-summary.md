---
title: Zusammenfassung der ToolStrip-Technologie
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], technology summary
- status bars [Windows Forms], technology summary
- toolbars [Windows Forms], technology summary
- menus [Windows Forms], technology summary
ms.assetid: e8d61973-7af9-429f-9df5-05a899c15a7b
ms.openlocfilehash: 26317fad5796989a58a48e4f26549805b279228a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213315"
---
# <a name="toolstrip-technology-summary"></a>Zusammenfassung der ToolStrip-Technologie
In diesem Thema sind Informationen zum `ToolStrip`-Steuerelement und den Klassen zusammengefasst, die seine Verwendung unterstützen.  
  
 Das `ToolStrip`-Steuerelement und die zugehörigen Klassen bieten eine umfassende Lösung für das Erstellen von Symbolleisten, Statusleisten und Menüs.  
  
## <a name="namespaces"></a>Namespaces  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
## <a name="background"></a>Hintergrund  
 Mit dem `ToolStrip`-Steuerelement und den zugehörigen Klassen können Sie erweiterte Symbolleistenfunktionen erstellen, die ein konsistentes und professionelles Aussehen und Verhalten aufweisen. Das `ToolStrip`-Steuerelement und die zugehörigen Klassen bieten gegenüber früheren Steuerelementen die folgenden Verbesserungen:  
  
-   Ein einheitlicheres Ereignismodell  
  
-   Ein konsistenteres Entwurfszeitverhalten, das Aufgabenlisten und Elementauflistungs-Editoren enthält  
  
-   Benutzerdefiniertes Rendern mit `ToolStripManager` und `ToolStripRenderer`  
  
-   Integriertes Rafting (die gemeinsame Nutzung eines horizontalen oder vertikalen Bereichs innerhalb des Toolbereichs im angedockten Zustand) mit `ToolStripContainer` und `ToolStripPanel`  
  
-   Die Neuanordnung von Elementen mit der <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>-Eigenschaft zur Entwurfs- und Laufzeit  
  
-   Das Umsetzen von Elementen in ein Überlaufmenü mit der <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>-Eigenschaft  
  
-   Vollständig konfigurierbare Steuerelementposition mit `ToolStripContainer`, `ToolStripPanel` und `ToolStripContentPanel`  
  
-   Das Hosten von `ToolStrip`-, traditionellen oder benutzerdefinierten Steuerelementen mithilfe von `ToolStripControlHost`  
  
-   Das Zusammenführen von `ToolStrip`Steuerelementen mithilfe von `ToolStripPanel`  
  
 `ToolStrip` ist die erweiterbare Basisklasse für `MenuStrip`, `ContextMenuStrip` und `StatusStrip`. Diese Steuerelemente sind <xref:System.Windows.Forms.ToolStripItem>-Container, die eine gemeinsame Verhaltensweise und die Ereignisbehandlung erben, die erweitert werden, damit sich jede Implementierung mit dem für sie geeigneten Verhalten beschäftigt. Die von <xref:System.Windows.Forms.ToolStripItem> abgeleiteten Steuerelemente sind in der folgenden Tabelle aufgeführt. Die `ToolStrip`-Basisklasse befasst sich mit Zeichenoperationen, Benutzereingaben und Drag & Drop-Ereignissen für diese Steuerelemente.  
  
 Die Steuerelemente `ToolStrip`, `MenuStrip`, `ContextMenuStrip` und `StatusStrip` ersetzen die vorherigen Symbolleisten-, Menü-, Kontextmenü- und Statusleistensteuerelemente, obwohl diese Steuerelemente im Hinblick auf die Abwärtskompatibilität beibehalten werden.  
  
## <a name="toolstrip-classes-at-a-glance"></a>ToolStrip-Klassen auf einen Blick  
 Die folgende Tabelle zeigt die nach Technologiebereich geordneten ToolStrip-Klassen.  
  
|Technologiebereich|Klasse|  
|---------------------|-----------|  
|Symbolleisten-, Status- und Menücontainer|<xref:System.Windows.Forms.ToolStrip><br /><br /> <xref:System.Windows.Forms.MenuStrip><br /><br /> <xref:System.Windows.Forms.ContextMenuStrip><br /><br /> <xref:System.Windows.Forms.StatusStrip><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownMenu>|  
|ToolStrip-Elemente|<xref:System.Windows.Forms.ToolStripLabel><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownItem><br /><br /> <xref:System.Windows.Forms.ToolStripMenuItem><br /><br /> <xref:System.Windows.Forms.ToolStripButton><br /><br /> <xref:System.Windows.Forms.ToolStripStatusLabel><br /><br /> <xref:System.Windows.Forms.ToolStripSeparator><br /><br /> <xref:System.Windows.Forms.ToolStripControlHost><br /><br /> <xref:System.Windows.Forms.ToolStripComboBox><br /><br /> <xref:System.Windows.Forms.ToolStripTextBox><br /><br /> <xref:System.Windows.Forms.ToolStripProgressBar><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownButton><br /><br /> <xref:System.Windows.Forms.ToolStripSplitButton>|  
|Speicherort|<xref:System.Windows.Forms.ToolStripContainer><br /><br /> <xref:System.Windows.Forms.ToolStripContentPanel><br /><br /> <xref:System.Windows.Forms.ToolStripPanel>|  
|Präsentation und Rendering|<xref:System.Windows.Forms.ToolStripManager><br /><br /> <xref:System.Windows.Forms.ToolStripRenderer><br /><br /> <xref:System.Windows.Forms.ToolStripProfessionalRenderer><br /><br /> <xref:System.Windows.Forms.ToolStripRenderMode><br /><br /> <xref:System.Windows.Forms.ToolStripManagerRenderMode>|  
  
## <a name="toolstrip-design-time-features"></a>ToolStrip-Entwurfszeitfunktionen  
 Die <xref:System.Windows.Forms.ToolStrip>-Steuerelementfamilie bietet eine Vielzahl von Tools und Vorlagen für die direkte Bearbeitung und definieren die Grundlage für die Benutzeroberfläche, sodass Sie schnell eine funktionierende Anwendung erstellen können.  
  
### <a name="task-dialog-boxes"></a>Aufgabendialogfelder  
 Wenn Sie in Visual Studio im Designer auf das Smarttag eines Steuerelements klicken, wird eine Aufgabenliste für den einfachen Zugriff auf viele häufig verwendete Befehle angezeigt.  
  
-   [MenuStrip-Aufgaben (Dialogfeld)](https://msdn.microsoft.com/library/ms233645\(v=vs.110\))  
  
-   [ToolStrip-Aufgaben (Dialogfeld)](https://msdn.microsoft.com/library/ms233648\(v=vs.110\))  
  
-   [ContextMenuStrip-Aufgaben (Dialogfeld)](https://msdn.microsoft.com/library/ms233646\(v=vs.110\))  
  
-   [StatusStrip-Aufgaben (Dialogfeld)](https://msdn.microsoft.com/library/ms233642\(v=vs.110\))  
  
-   [ToolStripContainer-Aufgaben (Dialogfeld)](https://msdn.microsoft.com/library/ms233647\(v=vs.110\))  
  
### <a name="items-collection-editors"></a>Elementauflistungs-Editoren  
 In Visual Studio, wenn Sie auf **Elemente bearbeiten** für den Task aus, oder mit der rechten Maustaste den-Steuerelement, und wählen **Elemente bearbeiten** im Kontextmenü die Option, wird der auflistungs-Editor für das Steuerelement angezeigt. Mithilfe von Auflistungs-Editoren können Sie Elemente zum Steuerelement hinzufügen, aus dem Steuerelement entfernen und die im Steuerelement enthaltenen Elemente neu anordnen. Zudem können Sie die Eigenschaften für das Steuerelement und für die Elemente des Steuerelements anzeigen und ändern.  
  
-   [MenuStrip-Elementauflistungs-Editor](https://msdn.microsoft.com/library/ms233625\(v=vs.110\))  
  
-   [StatusStrip-Elementauflistungs-Editor](https://msdn.microsoft.com/library/ms233631\(v=vs.110\))  
  
-   [ContextMenuStrip-Elementauflistungs-Editor](https://msdn.microsoft.com/library/ms233641\(v=vs.110\))  
  
-   [ToolStrip-Elementauflistungs-Editor](https://msdn.microsoft.com/library/ms233643\(v=vs.110\))  
  
## <a name="hosting-controls"></a>Hosten von Steuerelementen  
 Die <xref:System.Windows.Forms.ToolStripControlHost>-Klasse bietet integrierte Wrapper für die Steuerelemente <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox> und <xref:System.Windows.Forms.ToolStripProgressBar>. Sie können auch beliebige andere vorhandene Steuerelemente oder COM-Steuerelemente in einem <xref:System.Windows.Forms.ToolStripControlHost> hosten.  
  
 Ein Beispiel für das Steuerelement zu hosten, finden Sie unter [wie: Umschließen eines Windows Forms-Steuerelements ToolStripControlHost](../../../../docs/framework/winforms/controls/how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost.md).  
  
## <a name="rendering"></a>Rendern  
 <xref:System.Windows.Forms.ToolStrip>-Klassen implementieren ein Renderingschema, das sich von anderen Windows Forms-Steuerelementen erheblich unterscheidet. Mit diesem Schema können Formatvorlagen und Designs ganz einfach angewendet werden.  
  
 Um eine Formatvorlage auf ein <xref:System.Windows.Forms.ToolStrip> und alle darin enthaltenenen <xref:System.Windows.Forms.ToolStripItem>-Objekte anzuwenden, müssen Sie nicht das <xref:System.Windows.Forms.ToolStripItem.Paint>-Ereignis für die einzelnen Elemente behandeln. Stattdessen können Sie für die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>-Eigenschaft einen der <xref:System.Windows.Forms.ToolStripRenderMode>-Werte festlegen, der nicht <xref:System.Windows.Forms.ToolStripRenderMode.Custom> entspricht. Alternativ können Sie für <xref:System.Windows.Forms.ToolStrip.Renderer%2A> direkt eine beliebige Klasse festlegen, die von der <xref:System.Windows.Forms.ToolStripRenderer>-Klasse erbt. Durch Festlegen dieser Eigenschaft wird automatisch <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> festgelegt.  
  
 Sie können dieselbe Formatvorlage auf mehrere <xref:System.Windows.Forms.ToolStrip>-Objekte in derselben Anwendung anwenden, indem Sie für <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> den Wert <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> und für die Eigenschaft <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A> oder <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> den gewünschten <xref:System.Windows.Forms.ToolStripManagerRenderMode>-Wert oder entsprechend den <xref:System.Windows.Forms.ToolStripRenderer>-Wert festlegen.  
  
 Beispiele zum Rendering finden Sie unter [Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md).  
  
## <a name="styles-and-themes"></a>Formatvorlagen und Designs  
 <xref:System.Windows.Forms.ToolStrip> und die zugehörigen Klassen bieten eine einfache Möglichkeit zur Unterstützung von visuellen Formatvorlagen und der benutzerdefinierten Darstellung, für die die <xref:System.Windows.Forms.ToolStripItem.OnPaint%2A>-Methoden nicht für jedes Element außer Kraft gesetzt werden müssen. Verwenden Sie die Eigenschaften <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> und <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> und <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.  
  
## <a name="rafting-and-docking"></a>Rafting und Andocken  
 Sie können <xref:System.Windows.Forms.ToolStrip>-Steuerelemente per Rafting andocken, andocken oder absolut positionieren. <xref:System.Windows.Forms.ToolStrip>-Elemente werden vom <xref:System.Windows.Forms.ToolStrip.LayoutEngine%2A> des Containers angeordnet.  
  
 *Rafting* ist die Möglichkeit von Symbolleisten, horizontalen oder vertikalen Speicherplatz freizugeben. Eine Windows-Formular kann ein <xref:System.Windows.Forms.ToolStripContainer> besitzen, das auf der linken, rechten, oberen und unteren Seite des Formulars wiederum Bereiche zum Positionieren und Rafting von <xref:System.Windows.Forms.ToolStrip>-, <xref:System.Windows.Forms.MenuStrip>- und <xref:System.Windows.Forms.StatusStrip>-Steuerelementen aufweist. Mehrere <xref:System.Windows.Forms.ToolStrip>-Steuerelemente werden vertikal gestapelt, wenn sie im linken oder rechten <xref:System.Windows.Forms.ToolStripContainer> abgelegt werden. Wenn Sie sie im oberen oder unteren <xref:System.Windows.Forms.ToolStripContainer> ablegen, werden sie horizontal gestapelt. Sie können das zentrale <xref:System.Windows.Forms.ToolStripContentPanel> von <xref:System.Windows.Forms.ToolStripContainer> verwenden, um herkömmliche Steuerelemente auf dem Formular zu positionieren.  
  
 Einige oder alle <xref:System.Windows.Forms.ToolStripContainer>-Steuerelemente sind zur Entwurfszeit direkt auswählbar und können gelöscht werden. Ein <xref:System.Windows.Forms.ToolStripContainer> ist erweiterbar und reduzierbar und passt seine Größe an die darin enthaltenen Steuerelemente an.  
  
 *Andocken* bezeichnet die Angabe der einfachen Position eines Steuerelements, auf die Links, rechts, oben oder Unterseite des Formulars.  
  
 Der Vorteil des Raftings gegenüber dem Andocken ist, dass <xref:System.Windows.Forms.ToolStrip>-, <xref:System.Windows.Forms.MenuStrip>- und <xref:System.Windows.Forms.StatusStrip>-Steuerelemente den horizontalen oder vertikalen Bereich gemeinsam mit anderen Steuerelementen nutzen können.  
  
 Die meisten der <xref:System.Windows.Forms.ToolStrip>-Steuerelemente können wie andere Steuerelemente auf dem Formular angedockt werden, anstatt sie per Rafting anzudocken. Sie können zudem angeben, dass ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement auf dem Formular frei positioniert werden kann, indem Sie es aus seinem <xref:System.Windows.Forms.ToolStripContainer> entfernen und für seine `Dock`-Eigenschaft den Wert `None` festlegen. Sie können auch seine absolute Position angeben, indem Sie die entsprechende <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft festlegen. Finden Sie unter [Vorgehensweise: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular](../../../../docs/framework/winforms/controls/how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form.md).  
  
 Verwenden Sie ein oder mehrere <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente zum Erhöhen der Flexibilität, insbesondere für MDI-Anwendungen (Multiple Document Interface), oder für den Fall, dass Sie kein <xref:System.Windows.Forms.ToolStripContainer> benötigen. Ein <xref:System.Windows.Forms.ToolStripPanel> stellt einen andockbaren Bereich für die Suche und das Rafting von <xref:System.Windows.Forms.ToolStrip>-Steuerelementen bereit. Herkömmliche Steuerelemente sind hiervon jedoch ausgeschlossen. Standardmäßig die <xref:System.Windows.Forms.ToolStripPanel> wird im Designer nicht angezeigt **Toolbox**, aber Sie können es dort ablegen, indem Sie mit der rechten Maustaste die **Toolbox**, und klicken Sie dann auf **Elemente auswählen**. Sie können auch wie bei jeder anderen Klasse programmgesteuert auf <xref:System.Windows.Forms.ToolStripPanel> zugreifen.  
  
 Bei <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.StatusStrip> können Elemente überlaufen. Dies ist mit der Art und Weise vergleichbar, in der sich Elemente auf den Microsoft Office-Symbolleisten verhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Architektur des ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
