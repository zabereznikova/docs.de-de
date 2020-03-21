---
title: Abrufen von Benutzeroberflächenautomatisierungs-Elementen
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, obtaining elements
- elements, UI Automation, obtaining
ms.assetid: c2caaf45-e59c-42a1-bc9b-77a6de520171
ms.openlocfilehash: eab4e59ee219808a4c0ae9ca5331a14928b66b5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179997"
---
# <a name="obtaining-ui-automation-elements"></a>Abrufen von Benutzeroberflächenautomatisierungs-Elementen
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema werden die verschiedenen Möglichkeiten zum Abrufen von <xref:System.Windows.Automation.AutomationElement> -Objekten für [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Elemente beschrieben.  
  
> [!CAUTION]
> Wenn Ihre Clientanwendung nach Elementen in ihrer eigenen Benutzeroberfläche suchen kann, müssen alle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Aufrufe in einem separaten Thread ausgeführt werden. Weitere Informationen finden Sie unter [UI Automation Threading Issues](ui-automation-threading-issues.md).  
  
<a name="The_Root_Element"></a>
## <a name="root-element"></a>Root-Element  
 Für jede Suche nach <xref:System.Windows.Automation.AutomationElement> -Objekten ist ein Ausgangspunkt erforderlich. Dies kann ein beliebiges Element sein, z. B. der Desktop, ein Anwendungsfenster oder ein Steuerelement.  
  
 Das Stammelement für den Desktop, aus dem alle Elemente abgeleitet werden, wird aus der statischen <xref:System.Windows.Automation.AutomationElement.RootElement%2A?displayProperty=nameWithType> -Eigenschaft abgerufen.  
  
> [!CAUTION]
> Grundsätzlich sollten Sie nur versuchen, direkt untergeordnete Elemente des Elements abzurufen, das von der <xref:System.Windows.Automation.AutomationElement.RootElement%2A>-Eigenschaft angegeben wird. Eine Suche nach Nachfolgerelementen kann hunderte oder sogar tausende Elemente durchlaufen und möglicherweise einen Stapelüberlauf verursachen. Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.  
  
<a name="Using_Conditions"></a>
## <a name="conditions"></a>Bedingungen  
 In den meisten Verfahren, die zum Abrufen von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elementen verwendet werden können, müssen Sie eine <xref:System.Windows.Automation.Condition>angeben, die ein Satz von Kriterien ist, mit denen definiert wird, welche Elemente abgerufen werden sollen.  
  
 Die einfachste Bedingung ist <xref:System.Windows.Automation.Condition.TrueCondition>. Dies ist ein vordefiniertes Objekt, das angibt, dass alle im Suchbereich befindlichen Elemente zurückgegeben werden sollen. <xref:System.Windows.Automation.Condition.FalseCondition>(das Gegenteil von <xref:System.Windows.Automation.Condition.TrueCondition>) ist weniger nützlich, da diese Bedingung verhindert, dass irgendein Element gefunden wird.  
  
 Sie können drei weitere vordefinierte Bedingungen jeweils eigenständig oder in Kombination mit anderen Bedingungen verwenden: <xref:System.Windows.Automation.Automation.ContentViewCondition>, <xref:System.Windows.Automation.Automation.ControlViewCondition>und <xref:System.Windows.Automation.Automation.RawViewCondition>. Eigenständig verwendet entsprichtder Bedingung , da Elemente hierbei nicht nach ihrer  -Eigenschaft oder  -Eigenschaft gefiltert werden.  
  
 Andere Bedingungen werden aus <xref:System.Windows.Automation.PropertyCondition> -Objekten erstellt, von denen jedes einen Eigenschaftswert angibt. Beispielsweise kann ein <xref:System.Windows.Automation.PropertyCondition> -Objekt angeben, dass das Element aktiviert ist oder dass es bestimmtes Steuerelementmuster unterstützt.  
  
 Bedingungen können über boolesche Logik kombiniert werden, indem Objekte des Typs <xref:System.Windows.Automation.AndCondition>, <xref:System.Windows.Automation.OrCondition>oder <xref:System.Windows.Automation.NotCondition>erstellt werden.  
  
<a name="Search_Scope"></a>
## <a name="search-scope"></a>Suchbereich  
 Für Suchvorgänge, die mit <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> oder <xref:System.Windows.Automation.AutomationElement.FindAll%2A> ausgeführt werden, sind sowohl ein Bereich als auch ein Ausgangspunkt erforderlich.  
  
 Der Bereich definiert den zu durchsuchenden Raum um den Ausgangspunkt. Beispiele sind das Element selbst sowie die gleichgeordneten Elemente, das übergeordnete Element, die Vorgängerelemente, die direkt untergeordneten Elemente und die Nachfolgerelemente des Elements.  
  
 Der Bereich einer Suche wird durch eine bitweise Kombination von Werten aus der <xref:System.Windows.Automation.TreeScope> -Enumeration definiert.  
  
<a name="Finding_a_Known_Element"></a>
## <a name="finding-a-known-element"></a>Suchen nach einem bekannten Element  
 Ein bekanntes Element, das durch seine <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>-, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>- oder eine andere Eigenschaft bzw. ein Kombination von Eigenschaften gekennzeichnet ist, lässt sich am einfachsten mit der <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> -Methode finden. Wenn das gesuchte Element ein Anwendungsfenster ist, kann der Ausgangspunkt der Suche die <xref:System.Windows.Automation.AutomationElement.RootElement%2A>-Eigenschaft sein.  
  
 Dieses Verfahren zum Suchen nach [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elementen ist in Szenarios für automatisierte Tests am nützlichsten.  
  
<a name="Finding_Elements_in_a_Subtree"></a>
## <a name="finding-elements-in-a-subtree"></a>Suchen nach Elementen in einer Unterstruktur  
 Um alle Elemente zu finden, die bestimmten Kriterien in Bezug auf ein bekanntes Element entsprechen, können Sie <xref:System.Windows.Automation.AutomationElement.FindAll%2A>verwenden. Beispielsweise könnten Sie diese Methode verwenden, um Listenelemente oder Menüelemente aus einer Liste bzw. einem Menü abzurufen oder alle Steuerelemente in einem Dialogfeld zu ermitteln.  
  
<a name="Walking_a_Subtree"></a>
## <a name="walking-a-subtree"></a>Durchlaufen einer Unterstruktur  
 Wenn Sie nichts über die Anwendungen wissen, mit denen Ihr Client möglicherweise verwendet wird, können Sie über die <xref:System.Windows.Automation.TreeWalker> -Klasse eine Unterstruktur aller relevanten Elemente erstellen. Dies kann in Ihrer Anwendung als Reaktion auf ein Ereignis erfolgen, das durch eine Fokusänderung ausgelöst wurde. Das heißt, wenn eine Anwendung oder ein Steuerelement den Eingabefokus erhält, überprüft der Benutzeroberflächenautomatisierungs-Client die untergeordneten Elemente und möglicherweise alle Nachfolgerelemente des Elements mit Fokus.  
  
 Eine weitere Verwendungsmöglichkeit für <xref:System.Windows.Automation.TreeWalker> besteht darin, die Vorgänger eines Elements zu ermitteln. Beispielsweise können Sie das übergeordnete Fenster eines Steuerelements ermitteln, indem Sie die Struktur nach oben durchlaufen.  
  
 Sie können <xref:System.Windows.Automation.TreeWalker> verwenden, indem Sie entweder ein Objekt der Klasse erstellen (und dabei die relevanten Elemente durch Übergeben eines <xref:System.Windows.Automation.Condition>-Objekts definieren) oder eines der folgenden vordefinierten Objekte verwenden, die als Felder von <xref:System.Windows.Automation.TreeWalker>definiert sind.  
  
|||  
|-|-|  
|<xref:System.Windows.Automation.TreeWalker.ContentViewWalker>|Sucht nur nach Elementen, deren <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> -Eigenschaft gleich `true`ist.|  
|<xref:System.Windows.Automation.TreeWalker.ControlViewWalker>|Sucht nur nach Elementen, deren <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> -Eigenschaft gleich `true`ist.|  
|<xref:System.Windows.Automation.TreeWalker.RawViewWalker>|Sucht nach allen Elementen.|  
  
 Nachdem Sie ein <xref:System.Windows.Automation.TreeWalker>-Objekt abgerufen haben, ist dessen Verwendung unkompliziert. Rufen Sie einfach die `Get` -Methoden auf, um durch die Elemente der Unterstruktur zu navigieren.  
  
 Die <xref:System.Windows.Automation.TreeWalker.Normalize%2A> -Methode kann verwendet werden, um von einem Element, das nicht Teil der Ansicht ist, zu einem Element in der Unterstruktur zu navigieren. Nehmen Sie beispielsweise an, dass Sie mit <xref:System.Windows.Automation.TreeWalker.ContentViewWalker>eine Ansicht einer Unterstruktur erstellt haben. Ihre Anwendung empfängt dann eine Benachrichtigung, dass eine Scrollleiste den Eingabefokus erhalten hat. Weil eine Scrolllaufleiste aber kein Inhaltselement ist, fehlt sie in Ihrer Ansicht der Unterstruktur. Sie können das <xref:System.Windows.Automation.AutomationElement> , das die Scrolllaufleiste darstellt, jedoch an <xref:System.Windows.Automation.TreeWalker.Normalize%2A> übergeben und den unmittelbaren Vorgänger in der Inhaltsansicht abrufen.  
  
<a name="Other_Ways_to_Retrieve_an_Element"></a>
## <a name="other-ways-to-retrieve-an-element"></a>Weitere Möglichkeiten zum Abrufen eines Elements  
 Zusätzlich zu Suchvorgängen und Navigation kann ein <xref:System.Windows.Automation.AutomationElement> folgendermaßen abgerufen werden.  
  
### <a name="from-an-event"></a>Über ein Ereignis  
 Wenn Ihre Anwendung ein [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis empfängt, ist das an Ihren Ereignishandler übergebene Quellobjekt ein <xref:System.Windows.Automation.AutomationElement>. Wenn Sie beispielsweise Ereignisse abonniert haben, die durch Fokusänderung ausgelöst werden, wird das Element, das den Fokus erhalten hat, als Quelle an Ihren <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> übergeben.  
  
 Weitere Informationen finden Sie unter [Subscribe to UI Automation Events](subscribe-to-ui-automation-events.md).  
  
### <a name="from-a-point"></a>Über einen Punkt  
 Wenn Sie über Bildschirmkoordinaten (beispielsweise die Cursorposition) verfügen, können Sie ein <xref:System.Windows.Automation.AutomationElement> abrufen, indem Sie die statische <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> -Methode verwenden.  
  
### <a name="from-a-window-handle"></a>Über ein Fensterhandle  
 Um ein <xref:System.Windows.Automation.AutomationElement> aus einem HWND abzurufen, verwenden Sie die statische <xref:System.Windows.Automation.AutomationElement.FromHandle%2A> -Methode.  
  
### <a name="from-the-focused-control"></a>Über das Steuerelement mit Fokus  
 Sie können ein <xref:System.Windows.Automation.AutomationElement> , das das Steuerelement mit Fokus darstellt, aus der statischen <xref:System.Windows.Automation.AutomationElement.FocusedElement%2A> -Eigenschaft abrufen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker](navigate-among-ui-automation-elements-with-treewalker.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
