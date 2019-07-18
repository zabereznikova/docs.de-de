---
title: 'Optimieren der Leistung: Layout und Entwurf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
ms.openlocfilehash: a18cc364d625cc98f77e63b0f361980ef574e8a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611897"
---
# <a name="optimizing-performance-layout-and-design"></a>Optimieren der Leistung: Layout und Entwurf
Der Entwurf Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung kann die Leistung durch unnötigen Mehraufwand durch die Berechnung des Layouts und das Überprüfung von Objektverweisen beeinträchtigen. Das Erstellen von Objekten, insbesondere zur Laufzeit, kann sich auf die Leistungsmerkmale Ihrer Anwendung auswirken.  
  
 In diesem Thema erhalten Sie Empfehlungen bezüglich der Leistung in diesen Bereichen.  
  
## <a name="layout"></a>Layout  
 Der Begriff "Layoutdurchlauf" beschreibt den Prozess des Messens und Anordnens von Membern einer <xref:System.Windows.Controls.Panel>-abgeleiteten Auflistung der untergeordneten Elemente, und zeichnen Sie dann auf dem Bildschirm dargestellt. Ein Layoutdurchlauf ist ein mathematisch aufwändiger Prozess; je mehr untergeordnete Elementen sich in der Auflistung befinden, desto mehr Berechnungen sind erforderlich. Beispielsweise jedes Mal, wenn ein untergeordnetes Element <xref:System.Windows.UIElement> Objekt in der Auflistung seine Position ändert, müssen sie einen neuen Durchlauf des Layoutsystems auslösen. Aufgrund der engen Verbindung zwischen den Merkmalen des Objekts und dem Layoutverhalten ist es unumgänglich, den Ereignistyp zu verstehen, der das Layoutsystem aufrufen kann. Die Leistung Ihrer Anwendung wird optimiert, wenn Sie unnötige Aufrufe des Layoutdurchlaufs so weit wie möglich reduzieren.  
  
 Das Layoutsystem führt zwei Durchläufe für jeden untergeordneten Member in einer Auflistung durch: einen Messdurchlauf und einen Anordnungsdurchlauf. Jedes Objekt verfügt über seine eigene überschriebene Implementierung von der <xref:System.Windows.UIElement.Measure%2A> und <xref:System.Windows.UIElement.Arrange%2A> Methoden, um sein eigenes spezifisches Layoutverhalten bereitzustellen. Ganz einfach ausgedrückt bedeutet dies, dass Layout ein rekursives System ist, das die Größe und Position eines Elements anpasst und dieses auf dem Bildschirm zeichnet.  
  
- Ein untergeordnetes Element <xref:System.Windows.UIElement> Objekt startet den Layoutvorgang, indem zuerst dessen Kerneigenschaften gemessen.  
  
- Des Objekts <xref:System.Windows.FrameworkElement> Eigenschaften, die der Größe,, z. B. verknüpft sind <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, und <xref:System.Windows.FrameworkElement.Margin%2A>, ausgewertet werden.  
  
- <xref:System.Windows.Controls.Panel>-spezifische Logik angewendet wird, wie z. B. die <xref:System.Windows.Controls.DockPanel.Dock%2A> Eigenschaft der <xref:System.Windows.Controls.DockPanel>, oder die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft der <xref:System.Windows.Controls.StackPanel>.  
  
- Nachdem alle untergeordneten Objekte ausgemessen wurden, wird der Inhalt angeordnet oder positioniert.  
  
- Die Auflistung der untergeordneten Objekte wird auf dem Bildschirm dargestellt.  
  
 Der Layoutdurchlauf wird erneut aufgerufen, wenn eine der folgenden Aktionen ausgeführt wird:  
  
- Ein untergeordnetes Objekt wird der Auflistung hinzugefügt.  
  
- Ein <xref:System.Windows.FrameworkElement.LayoutTransform%2A> auf das untergeordnete Objekt angewendet wird.  
  
- Die <xref:System.Windows.UIElement.UpdateLayout%2A> Methode für das untergeordnete Objekt aufgerufen wird.  
  
- Wenn sich der Wert einer Abhängigkeitseigenschaft ändert, die mit Metadaten markiert ist, die die Messungs- oder Anordnungsdurchläufe beeinflussen  
  
### <a name="use-the-most-efficient-panel-where-possible"></a>Verwenden Sie das effizienteste Panel soweit möglich  
 Die Komplexität im Layoutprozess basiert direkt auf das Layoutverhalten der <xref:System.Windows.Controls.Panel>-abgeleitete Elemente, die Sie verwenden. Z. B. eine <xref:System.Windows.Controls.Grid> oder <xref:System.Windows.Controls.StackPanel> Steuerelement bietet viel mehr Funktionen als ein <xref:System.Windows.Controls.Canvas> Steuerelement. Für diese erhöhte Funktionalität büßen Sie an Leistung ein. Jedoch wenn Sie nicht die Funktionalität benötigen, die eine <xref:System.Windows.Controls.Grid> Steuerelement bereitgestellt werden, sollten Sie weniger leistungsaufwändige alternativen verwenden, z. B. Verwenden einer <xref:System.Windows.Controls.Canvas> oder ein benutzerdefiniertes Panel.  
  
 Weitere Informationen finden Sie unter [Übersicht über Panel-Elemente](../controls/panels-overview.md).  
  
### <a name="update-rather-than-replace-a-rendertransform"></a>Aktualisieren Sie RenderTransform, statt es zu ersetzen  
 Möglicherweise zum Aktualisieren einer <xref:System.Windows.Media.Transform> statt zu ersetzen es als Wert für eine <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft. Dies gilt besonders für Szenarios mit Animation. Durch das Aktualisieren einer vorhandenen <xref:System.Windows.Media.Transform>, Sie vermeiden, Initiieren einer unnötigen layoutberechnung.  
  
### <a name="build-your-tree-top-down"></a>Erstellen Sie Ihre Struktur von oben nach unten  
 Wenn der logischen Struktur ein Knoten hinzugefügt oder dieser entfernt wird, werden Eigenschafteninvalidierungen auf dem übergeordneten und allen untergeordneten Elementen des Knotens ausgelöst. Demzufolge sollte immer ein Oben-nach-unten-Erstellmuster eingehalten werden, um unnötige Invalidierungen auf Knoten zu verhindern, die bereits validiert wurden. Die folgende Tabelle zeigt den Unterschied in der ausführungsgeschwindigkeit zwischen dem Erstellen einer Struktur von oben nach unten und von unten nach oben, in denen die Struktur 150 Ebenen mit einem einzelnen ist <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.DockPanel> auf jeder Ebene.  
  
|**Aktion**|**Strukturerstellung (in ms)**|**Rendern, einschließlich Strukturerstellung (in ms)**|  
|----------------|---------------------------------|-------------------------------------------------|  
|Unten-nach-oben|366|454|  
|Oben-nach-unten|11|96|  
  
 Im folgenden Code wird veranschaulicht, wie Sie eine Struktur von oben nach unten erstellen können.  
  
 [!code-csharp[Performance#PerformanceSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](trees-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
- [Layout](layout.md)
