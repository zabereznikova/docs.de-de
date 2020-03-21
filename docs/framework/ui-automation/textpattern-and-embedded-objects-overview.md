---
title: Übersicht über TextPattern und eingebettete Objekte
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, TextPattern class
- embedded objects, accessing
- accessing embedded objects
- embedded objects, UI Automation
ms.assetid: 93fdfbb9-0025-4b72-8ca0-0714adbb70d5
ms.openlocfilehash: 635c06a03107b33134b015e2643c5281dd86798b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180013"
---
# <a name="textpattern-and-embedded-objects-overview"></a>Übersicht über TextPattern und eingebettete Objekte
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In dieser Übersicht wird beschrieben, wie von der [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] eingebettete Objekte oder untergeordnete Elemente innerhalb eines Textdokuments oder Containers verfügbar gemacht werden.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] einem eingebetteten Objekt ist jedes Element, das nicht textbezogene Grenzen hat. z. B. ein Bild, ein Hyperlink, eine Tabelle oder ein Dokumenttyp, z. B. eine Microsoft Excel-Tabelle oder eine Microsoft Windows Media-Datei. Dies weicht von der Standarddefinition ab, in der Elemente in einer Anwendung erstellt und einer anderen eingebettet bzw. mit einer anderen verknüpft sind. Ob das Objekt innerhalb der ursprünglichen Anwendung bearbeitet werden kann, ist im Kontext der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht relevant.  
  
<a name="Embedded_Objects_and_the_UI_Automation_Tree"></a>
## <a name="embedded-objects-and-the-ui-automation-tree"></a>Eingebettete Objekte und die Benutzeroberflächenautomatisierungs-Struktur  
 Eingebettete Objekte werden als einzelne Elemente innerhalb der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur behandelt. Sie werden als untergeordnete Elemente des Textcontainers verfügbar gemacht, sodass über dasselbe Model wie bei anderen Steuerelementen in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]auf diese zugegriffen werden kann.  
  
 ![Eingebettete Tabelle mit Bild in einem Textcontainer](./media/uia-textpattern-embedded-objects-overview-example1.png "UIA_TextPattern_Embedded_Objects_Overview_Example1")  
Beispiel für einen Textcontainer mit Tabelle, Bild und eingebetteten Linkobjekten  
  
 ![Inhaltsansicht für das vorherige Beispiel](./media/uia-textpattern-embedded-objects-overview-example2.PNG "UIA_TextPattern_Embedded_Objects_Overview_Example2")  
Beispiel der Inhaltsansicht für einen Teil des vorherigen Textcontainers  
  
<a name="Expose_Embedded_Objects_Using_TextPattern_and"></a>
## <a name="expose-embedded-objects-using-textpattern-and-textpatternrange"></a>Verfügbarmachen von eingebetteten Objekten mithilfe von TextPattern und TextPatternRange  
 Die <xref:System.Windows.Automation.TextPattern> -Steuerelementmuster-Klasse wird in Verbindung mit der <xref:System.Windows.Automation.Text.TextPatternRange> -Klasse verwendet, um Methoden und Eigenschaften verfügbar zu machen, die das Navigieren und Abfragen von eingebetteten Objekten erleichtern.  
  
 Der Textinhalt (oder innere Text) eines Textcontainers und ein eingebettetes Objekt, z. B. ein Link oder eine Tabellenzelle, werden in der Steuerelementansicht und der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur als einzelner, kontinuierlicher Textstream verfügbar gemacht, Objektgrenzen werden dabei ignoriert. Wenn ein Benutzeroberflächenautomatisierungs-Client den Text abruft, um ihn zu lesen, zu interpretieren oder zu analysieren, sollte der Textbereich auf bestimmte Fälle überprüft werden, z. B. auf Tabellen mit Textinhalt oder andere eingebettete Objekte. Dies geschieht durch Aufrufen von <xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A> , um ein <xref:System.Windows.Automation.AutomationElement> für alle eingebetteten Elemente abzurufen, und anschließend durch Aufrufen von <xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> , um einen Textbereich für alle Elemente abzurufen. Dies wird rekursiv ausgeführt, bis der gesamte Textinhalt abgerufen wurde.  
  
 ![Von eingebetteten Objekten umfasste Textbereiche.](./media/uia-textpattern-embeddedobjecttextranges.png "UIA_TextPattern_EmbeddedObjectTextRanges")  
Beispiel für einen Textstream mit eingebetteten Objekten und deren Bereichsabschnitten  
  
 Wenn der Inhalt eines Textbereichs durchlaufen werden muss, ist eine Reihe von Hintergrundschritten erforderlich, um die <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> -Methode erfolgreich auszuführen.  
  
1. Der Textbereich ist normalisiert. Dies bedeutet, dass dieser auf einen degenerierten Bereich am <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> -Endpunkt reduziert ist, wodurch der <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> -Endpunkt überflüssig wird. Dieser Schritt ist notwendig, um Mehrdeutigkeiten in <xref:System.Windows.Automation.Text.TextUnit> Situationen zu entfernen, in denen ein Textbereich Grenzen überschreitet, z. B. `{The URL https://www.microsoft.com is embedded in text` wenn "-" und "-" die Textbereichsendpunkte sind.  
  
2. Der resultierende Bereich wird im <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> zurück an den Anfang der angeforderten <xref:System.Windows.Automation.Text.TextUnit> -Grenze verschoben.  
  
3. Der Bereich wird um die angeforderte Anzahl von <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> -Grenzen nach vorne oder nach hinten im <xref:System.Windows.Automation.Text.TextUnit> verschoben.  
  
4. Anschließend wird der Bereich von einem degenerierten Bereichszustand erweitert, indem der <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> -Endpunkt um eine angeforderte <xref:System.Windows.Automation.Text.TextUnit> -Grenze verschoben wird.  
  
 ![Bereichsanpassungen durch Verschieben & ExpandToEnclosingUnit](./media/uia-textpattern-moveandexpand-examples.png "UIA_TextPattern_MoveAndExpand_Examples")  
Beispiele für die Anpassung eines Textbereichs für Move() und ExpandToEnclosingUnit()  
  
<a name="Common_Scenarios"></a>
## <a name="common-scenarios"></a>Häufige Szenarios  
 In den folgenden Abschnitten sind Beispiele für die häufigsten Szenarien dargestellt, in denen eingebettete Objekte verwendet werden.  
  
 Legende für die dargestellten Beispiele:  
  
 { = <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start>  
  
 } = <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End>  
  
### <a name="hyperlink"></a>Link  

**Beispiel 1: Ein Textbereich, der einen eingebetteten Textlink enthält**
  
`{The URL https://www.microsoft.com is embedded in text}.`
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Gibt die Zeichenfolge `The URL https://www.microsoft.com is embedded in text` zurück.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Gibt das den Textbereich einschließende, innerste <xref:System.Windows.Automation.AutomationElement> zurück, in diesem Fall das <xref:System.Windows.Automation.AutomationElement> , das den Textanbieter darstellt.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Gibt ein <xref:System.Windows.Automation.AutomationElement> zurück, das das Linksteuerelement darstellt.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> , wobei <xref:System.Windows.Automation.AutomationElement> das von der vorherigen `GetChildren` -Methode zurückgegebene Objekt ist.|Gibt den Bereichhttps://www.microsoft.comzurück, der " darstellt.|  
  
 **Beispiel 2: Ein Textbereich, der einen eingebetteten Textlink nur teilweise enthält**  
  
 Die `https://{[www]}` URL ist in Text eingebettet.  
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Gibt die Zeichenfolge „www“ zurück.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Gibt das den Textbereich einschließende, innerste <xref:System.Windows.Automation.AutomationElement> zurück, in diesem Fall das Linksteuerelement.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Gibt `null` zurück, da der Textbereich nicht die gesamte URL-Zeichenfolge umfasst.|  
  
**Beispiel 3 : Ein Textbereich, der teilweise den Inhalt eines Textcontainers umfasst. Der Textcontainer verfügt über einen eingebetteten Text-Hyperlink, der nicht Teil des Textbereichs ist.**  
  
`{The URL} [https://www.microsoft.com](https://www.microsoft.com) is embedded in text.`
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Gibt die Zeichenfolge „Die URL“ zurück.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Gibt das den Textbereich einschließende, innerste <xref:System.Windows.Automation.AutomationElement> zurück, in diesem Fall das <xref:System.Windows.Automation.AutomationElement> , das den Textanbieter darstellt.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> mit den Parametern (TextUnit.Word, 1).|Verschiebt den Textbereichsabschnitt nach „http“, da der Text des Links aus einzelnen Wörtern besteht. In diesem Fall wird der Link nicht als einzelnes Objekt behandelt.<br /><br /> Die URL "[http]" ist in Text eingebettet.|  
  
<a name="Image"></a>
### <a name="image"></a>Image  
 **Beispiel 1: Ein Textbereich, der ein eingebettetes Bild enthält**  
  
 "Das ![eingebettete Bildbeispiel](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample") ist in Text eingebettet.  
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Gibt die Zeichenfolge „Das Bild ist in den Text eingebettet“ zurück. Ein dem Bild zugeordneter Alternativtext (ALT) kann nicht im Textstream miteingeschlossen werden.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Gibt das den Textbereich einschließende, innerste <xref:System.Windows.Automation.AutomationElement> zurück, in diesem Fall das <xref:System.Windows.Automation.AutomationElement> , das den Textanbieter darstellt.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Gibt ein <xref:System.Windows.Automation.AutomationElement> zurück, das das Bildsteuerelement darstellt.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> , wobei <xref:System.Windows.Automation.AutomationElement> das von der vorherigen <xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A> -Methode zurückgegebene Objekt ist.|Gibt den degenerierten Bereich zurück, der "![Embedded Image Example](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample")" darstellt.|  
  
 **Beispiel 2 : Ein Textbereich, der teilweise den Inhalt eines Textcontainers umfasst. Der Textcontainer verfügt über ein eingebettetes Bild, das nicht Teil des Textbereichs ist.**  
  
 "Das Bild" ![Eingebettetes Bildbeispiel](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample") ist in Text eingebettet.  
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Gibt die Zeichenfolge „Das Bild“ zurück.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Gibt das den Textbereich einschließende, innerste <xref:System.Windows.Automation.AutomationElement> zurück, in diesem Fall das <xref:System.Windows.Automation.AutomationElement> , das den Textanbieter darstellt.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> mit den Parametern (TextUnit.Word, 1).|Verschiebt den Textbereichsabschnitt nach „ist“. Da nur textbasierte eingebettete Objekte als Teil des Textstreams betrachtet werden, hat das Bild in diesem Beispiel keine Auswirkungen auf das Move-Objekt oder dessen Rückgabewert (in diesem Fall 1).|  
  
<a name="Table"></a>
### <a name="table"></a>Tabelle  
  
### <a name="table-used-for-examples"></a>Für Beispiele verwendete Tabelle  
  
|Zelle mit Bild|Zelle mit Text|  
|---------------------|--------------------|  
|![Beispiel für eingebettetes Bild](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample")|X|  
|![Beispiel 2 für eingebettetes Bild](./media/uia-textpattern-embedded-objects-overview-imageexample2.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample2")|J|  
|![Beispiel 3 für eingebettetes Bild](./media/uia-textpattern-embedded-objects-overview-imageexample3.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample3")<br /><br /> Bild für Z|Z|  
  
 **Beispiel 1: Abrufen des Textcontainers aus dem Inhalt einer Zelle**  
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.GridPattern.GetItem%2A> mit den Parametern (0,0)|Gibt das <xref:System.Windows.Automation.AutomationElement> zurück, das den Inhalt der Tabellenzelle darstellt; in diesem Fall ist das Element ein Textsteuerelement.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> , wobei <xref:System.Windows.Automation.AutomationElement> das von der vorherigen `GetItem` -Methode zurückgegebene Objekt ist.|Gibt den Bereich zurück, der das ![Bild Embedded Image Example](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample")umfasst.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> für das von der vorherigen `RangeFromChild` -Methode zurückgegebene Objekt.|Gibt das <xref:System.Windows.Automation.AutomationElement> zurück, das die Tabellenzelle darstellt; in diesem Fall ist das Element ein Textsteuerelement, das TableItemPattern unterstützt.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> für das von der vorherigen `GetEnclosingElement` -Methode zurückgegebene Objekt.|Gibt das <xref:System.Windows.Automation.AutomationElement> zurück, das die Tabelle darstellt.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> für das von der vorherigen `GetEnclosingElement` -Methode zurückgegebene Objekt.|Gibt das <xref:System.Windows.Automation.AutomationElement> zurück, das den Textanbieter darstellt.|  
  
 **Beispiel 2: Abrufen des Textinhalts einer Zelle**  
  
|Aufgerufene Methode|Ergebnis|  
|-------------------|------------|  
|<xref:System.Windows.Automation.GridPattern.GetItem%2A> mit den Parametern {1,1}.|Gibt das <xref:System.Windows.Automation.AutomationElement> zurück, das den Inhalt der Tabellenzelle darstellt; in diesem Fall ist das Element ein Textsteuerelement.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> , wobei <xref:System.Windows.Automation.AutomationElement> das von der vorherigen `GetItem` -Methode zurückgegebene Objekt ist.|Gibt „Y“ zurück.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.TextPattern>
- <xref:System.Windows.Automation.Text.TextPatternRange>
- <xref:System.Windows.Automation.Provider.ITextProvider>
- <xref:System.Windows.Automation.Provider.ITextRangeProvider>
- [Zugreifen auf eingebettete Objekte mit Benutzeroberflächenautomatisierung](access-embedded-objects-using-ui-automation.md)
- [Verfügbarmachen eines Tabelleninhalts durch Benutzeroberflächenautomatisierung](expose-the-content-of-a-table-using-ui-automation.md)
- [Durchlaufen von Text mit Benutzeroberflächenautomatisierung](traverse-text-using-ui-automation.md)
- [TextPattern-Such- und Auswahlbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FindText)
