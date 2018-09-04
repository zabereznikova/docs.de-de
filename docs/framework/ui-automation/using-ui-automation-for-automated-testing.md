---
title: Verwenden von Benutzeroberflächenautomatisierung für automatisierte Tests
ms.date: 03/30/2017
helpviewer_keywords:
- automated testing
- testing, UI Automation
- UI Automation, automated testing
ms.assetid: 3a0435c0-a791-4ad7-ba92-a4c1d1231fde
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2fe3d511b92ff055e80999fa498c24a44f771ebf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503367"
---
# <a name="using-ui-automation-for-automated-testing"></a>Verwenden von Benutzeroberflächenautomatisierung für automatisierte Tests
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In dieser Übersicht wird erläutert, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] als nützliches Framework für den programmgesteuerten Zugriff in Szenarien mit automatisierten Tests verwendet werden kann.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stellt ein einheitliches Objektmodell zur Verfügung, das allen [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Frameworks ermöglicht, komplexe, umfangreiche Funktionalität einfach und leicht automatisierbar bereitzustellen.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] wurde als Nachfolger von [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]entwickelt. [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] ist ein vorhandenes Framework, das zum Bereitstellen einer Lösung für den Zugriff auf Steuerelemente und Anwendungen entwickelt wurde. [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] wurde nicht im Hinblick auf Testautomatisierung entwickelt, obwohl es diese Rolle aufgrund der sehr ähnlichen Anforderungen hinsichtlich Zugriff und Automatisierung übernommen hat. Neben der Bereitstellung von verbesserten Zugriffslösungen wurde[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]insbesondere für stabile Funktionalität bei automatisierten Tests entwickelt. Beispielsweise wird in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] eine einzelne Schnittstelle zum Bereitstellen von Benutzeroberflächeninformationen und zum Erfassen der erforderlichen Informationen für AT-Produkte verwendet. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sind die beiden Modelle getrennt.  
  
 Sowohl ein Anbieter als auch ein Client müssen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] implementieren, damit es als automatisiertes Testtool eingesetzt werden kann. Benutzeroberflächenautomatisierungs-Anbieter sind Anwendungen, wie zum Beispiel Microsoft Word, Excel und andere Anwendungen oder Steuerelemente von Drittanbietern, die auf dem [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] -Betriebssystem basieren. Benutzeroberflächenautomatisierungs-Clients schließen automatisierte Testskripts und Hilfstechnologieanwendungen ein.  
  
> [!NOTE]
>  In dieser Übersicht sollen die neuen und verbesserten Testfunktionen von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]hervorgehoben werden. Diese Übersicht ist nicht zur Bereitstellung von Informationen über Barrierefreiheitsfeatures vorgesehen. Barrierefreiheitsfeatures werden nur wenn nötig erläutert.  
  
<a name="Using_UI_Automation_During_Development"></a>   
## <a name="ui-automation-in-a-provider"></a>Benutzeroberflächenautomatisierung in einem Anbieter  
 Zum Automatisieren von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] muss der Entwickler einer Anwendung bzw. eines Steuerelements ermitteln, welche Aktionen der Endbenutzer mit standardmäßiger Tastatur- und Mausinteraktion für das [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Objekt ausführen kann.  
  
 Nachdem diese wichtigen Aktionen ermittelt wurden, sollten entsprechende [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster (das heißt, die Steuerelementmuster, die Funktionalität und Verhalten des [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elements widerspiegeln) im Steuerelement implementiert werden. Beispielsweise beinhaltet die Interaktion mit einem Kombinationsfeld-Steuerelement (z. B. das Dialogfeld "Ausführen") in der Regel das Erweitern und Reduzieren, um eine Liste von Elementen ein- oder auszublenden, das Auswählen eines Elements aus dieser Liste oder das Hinzufügen eines neuen Werts per Tastatureingabe.  
  
> [!NOTE]
>  Bei anderen Barrierefreiheitsmodellen müssen Entwickler Informationen direkt von einzelnen Schaltflächen, Menüs oder anderen Steuerelementen erfassen. Leider weist jeder Steuerelementtyp viele Varianten mit kleinen Unterschieden auf. Anders ausgedrückt müssen zehn Varianten eines PushButtons, obwohl sie möglicherweise genau gleich funktionieren und den gleichen Zweck erfüllen, alle als eigene Steuerelemente behandelt werden. Es gibt keine Möglichkeit festzustellen, dass diese Steuerelemente über identische Funktionsweisen verfügen. Steuerelementmuster wurden entwickelt, um diese allgemeinen Steuerelementverhaltensweisen darzustellen. Weitere Informationen finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
<a name="Implementing_UI_Automation"></a>   
### <a name="implementing-ui-automation"></a>Implementieren von Benutzeroberflächenautomatisierung  
 Wie bereits erwähnt benötigen Testtools und Entwickler ohne das vereinheitlichte, von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]zur Verfügung gestellte Modell Framework-spezifische Informationen, um Eigenschaften und Verhalten von Steuerelementen in diesem Framework verfügbar zu machen. Da verschiedene Benutzeroberflächen-Frameworks zum gleichen Zeitpunkt innerhalb von Windows-Betriebssystemen vorhanden sein können, einschließlich [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)], als auch Windows Presentation Foundation (WPF), kann eine schwierige Aufgabe, mehrere Anwendungen mit testen Steuerelemente, die ähnlich erscheinen. In der folgenden Tabelle werden beispielsweise Framework-spezifische Eigenschaftennamen, die zum Abrufen des einem Schaltflächen-Steuerelement zugeordneten Namens (oder Texts) erforderlich sind, und die entsprechende einzelne, gleichwertige [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft aufgeführt.  
  
|Steuerelementtyp der Benutzeroberflächenautomatisierung|Benutzeroberflächen-Framework|Framework-spezifische Eigenschaft|Benutzeroberflächenautomatisierungs-Eigenschaft|  
|--------------------------------|------------------|---------------------------------|----------------------------|  
|Schaltfläche|Windows Presentation Foundation|Inhalt|NameProperty|  
|Schaltfläche|Win32|Beschriftung|NameProperty|  
|Bild|HTML|alt|NameProperty|  
  
 Benutzeroberflächenautomatisierungs-Anbieter sind für die Zuordnung der Framework-spezifischen Eigenschaften ihrer Steuerelemente zu den entsprechenden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften zuständig.  
  
 Informationen zum Implementieren von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] in einem Anbieter finden Sie unter [UI Automation Providers for Managed Code](../../../docs/framework/ui-automation/ui-automation-providers-for-managed-code.md). Informationen zum Implementieren von Steuerelementmustern finden Sie unter [UI Automation Control Patterns](../../../docs/framework/ui-automation/ui-automation-control-patterns.md) und [UI Automation Text Pattern](../../../docs/framework/ui-automation/ui-automation-text-pattern.md).  
  
<a name="Testing_with_UI_Automation"></a>   
## <a name="ui-automation-in-a-client"></a>Benutzeroberflächenautomatisierung in einem Client  
 Das Ziel vieler automatisierter Testtools und entsprechender Szenarien ist die konsistente und wiederholbare Bearbeitung der Benutzeroberfläche. Dies kann Komponententests bestimmter Steuerelemente bis hin zum Aufzeichnen und Anwenden von Testskripts umfassen, durch die eine Iteration einer Reihe allgemeiner Aktionen auf einer Steuerelementgruppe ausgeführt wird.  
  
 Eine sich aus automatisierten Anwendungen ergebende Schwierigkeit ist das Synchronisieren eines Tests mit einem dynamischen Ziel. Ein Beispiel hierfür ist ein Listenfeld-Steuerelement, z. B. das im Windows Task-Manager angezeigte Feld mit der Liste der derzeit ausgeführten Anwendungen. Da die Einträge im Listenfeld unabhängig von der Steuerung durch die Testanwendung dynamisch aktualisiert werden, ist es nicht möglich, die Auswahl eines bestimmten Eintrags konsistent zu wiederholen. Ähnliche Probleme können auch beim Wiederholen einfacher Fokusänderungen in [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] auftreten, das nicht der Steuerung durch die Testanwendung unterliegt.  
  
<a name="Programmatic_Access"></a>   
### <a name="programmatic-access"></a>Programmgesteuerter Zugriff  
 Mit programmgesteuertem Zugriff können mithilfe von Code alle durch normale Maus- und Tastatureingaben ausführbaren Interaktionen und Verhaltensweisen imitiert werden. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglich programmgesteuerten Zugriff mit fünf Komponenten:  
  
-   Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur erleichtert die Navigation durch die Struktur von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Die Struktur wird aus der hWnd-Auflistung erstellt. Weitere Informationen finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
  
-   Automatisierungselemente sind einzelne Komponenten im [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Diese sind oft feiner unterteilt als ein hWnd. Weitere Informationen finden Sie unter [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md).  
  
-   Automatisierungseigenschaften stellen bestimmte Informationen über [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente bereit. Weitere Informationen finden Sie unter [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
-   Mit Steuerelementmustern wird ein bestimmter Aspekt der Funktionalität eines Steuerelements definiert. Sie können aus Informationen zu Eigenschaften, Methoden, Ereignissen und Struktur bestehen. Weitere Informationen finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
-   Automatisierungsereignisse stellen Ereignisbenachrichtigungen und Informationen bereit. Weitere Informationen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Key_properties_critical_to_test_automation"></a>   
### <a name="key-properties-for-test-automation"></a>Haupteigenschaften für die Testautomatisierung  
 Die Möglichkeit, jedes Steuerelement in [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] eindeutig zu identifizieren und anschließend zu finden, stellt die Grundlage für das Ausführen automatisierter Testanwendungen auf [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]dar. Es gibt hierfür mehrere hilfreiche [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Eigenschaften, die von unterstützenden Clients und Anbietern verwendet werden.  
  
#### <a name="automationid"></a>AutomationID  
 Unterscheidet ein Automatisierungselement von den nebengeordneten Elementen. <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> ist nicht lokalisiert, im Gegensatz zu Eigenschaften wie <xref:System.Windows.Automation.AutomationElement.NameProperty> , die in der Regel lokalisiert werden, wenn ein Produkt in mehreren Sprachen ausgeliefert wird. Siehe [Use the AutomationID Property](../../../docs/framework/ui-automation/use-the-automationid-property.md).  
  
> [!NOTE]
>  Durch<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> wird keine eindeutige Identität in der gesamten Automatisierungsstruktur sichergestellt. Eine Anwendung kann beispielsweise ein Menüsteuerelement mit mehreren Menüeinträgen oberster Ebene enthalten, die wiederum mehrere untergeordnete Menüeinträge aufweisen. Diese sekundären Menüeinträge können durch ein allgemeines Schema wie "Element1, Element2, Element3 usw." identifiziert werden, wodurch doppelte Bezeichner für die untergeordneten Elemente aller Menüeinträge oberster Ebene möglich sind.  
  
#### <a name="controltype"></a>ControlType  
 Identifiziert den Steuerelementtyp, der durch ein Automatisierungselement dargestellt wird. Durch Kenntnis des Steuerelementtyps können wichtige Informationen abgeleitet werden. Siehe [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md).  
  
#### <a name="nameproperty"></a>NameProperty  
 Dies ist eine Textzeichenfolge, die ein Steuerelement identifiziert oder erläutert. <xref:System.Windows.Automation.AutomationElement.NameProperty> sollte mit Vorsicht verwendet werden, da möglicherweise eine Lokalisierung vorliegt. Siehe [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="Steps_Required_To_Automate_the_UI_in_a_Test_Application"></a>   
### <a name="implementing-ui-automation-in-a-test-application"></a>Implementieren von Benutzeroberflächenautomatisierung in einer Testanwendung  
  
|||  
|-|-|  
|Fügen Sie die Benutzeroberflächenautomatisierungs-Verweise hinzu.|Die erforderlichen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -DLLs für Benutzeroberflächenautomatisierungs-Clients sind hier aufgeführt.<br /><br /> -UIAutomationClient.dll bietet Zugriff auf die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clientseitigen APIs.<br />-Die UIAutomationClientSideProvider.dll bietet die Möglichkeit zum Automatisieren von [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente. Siehe [UI Automation Support for Standard Controls](../../../docs/framework/ui-automation/ui-automation-support-for-standard-controls.md).<br />-UIAutomationTypes.dll bietet Zugriff auf bestimmten in definierten Typen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|Fügen Sie den <xref:System.Windows.Automation> -Namespace hinzu.|Dieser Namespace enthält alle Komponenten, die Benutzeroberflächenautomatisierungs-Clients zum Verwenden der Funktionen von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] benötigen, mit Ausnahme von Textbehandlung.|  
|Fügen Sie den <xref:System.Windows.Automation.Text> -Namespace hinzu.|Dieser Namespace enthält alle Komponenten, die Benutzeroberflächenautomatisierungs-Clients zum Verwenden der Funktionen der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textbehandlung benötigen.|  
|Suchen relevanter Steuerelemente|Automatisierte Testskripts suchen Benutzeroberflächenautomatisierungs-Clients, die relevante Steuerelemente in der Automatisierungsstruktur darstellen.<br /><br /> Es gibt mehrere Möglichkeiten, Benutzeroberflächenautomatisierungs-Elemente mit Code zu erhalten.<br /><br /> -Abfragen die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mithilfe einer <xref:System.Windows.Automation.Condition> Anweisung. Dies wird in der Regel bei sprachneutraler <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> verwendet. **Hinweis:** ein <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> erhalten Sie mithilfe eines Tools wie Inspect.exe, die zum aufschlüsseln kann die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften eines Steuerelements. <br /><br /> – Verwenden Sie die <xref:System.Windows.Automation.TreeWalker> Klasse, um die gesamte durchlaufen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur oder eine Teilmenge davon.<br />– Verfolgen Sie den Fokus.<br />– Verwenden Sie das hWnd des Steuerelements.<br />– Verwenden Sie die Bildschirmposition, z. B. die Position des Mauszeigers.<br /><br /> Siehe [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md).|  
|Abrufen von Steuerelementmustern|Steuerelementmuster machen allgemeine Verhalten für Steuerelemente mit ähnlichen Funktionen verfügbar.<br /><br /> Wenn die zu testenden Steuerelemente gefunden wurden, können mit automatisierten Testskripts die relevanten Steuerelementmuster dieser Benutzeroberflächenautomatisierungs-Elemente abgerufen werden. Zum Beispiel das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster für typische Schaltflächenfunktionalität oder das <xref:System.Windows.Automation.WindowPattern> -Steuerelementmuster für Fensterfunktionalität.<br /><br /> Siehe [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).|  
|Automatisieren der Benutzeroberfläche|Automatisierte Testskripts können nun alle relevanten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] von einem [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Framework steuern. Hierfür werden die von den [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmustern verfügbar gemachten Informationen und Funktionen verwendet.|  
  
<a name="Supporting_tools"></a>   
## <a name="related-tools-and-technologies"></a>Verwandte Tools und Technologien  
 Es gibt eine Reihe verwandter Tools und Technologien, die automatisierte Tests mit [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]unterstützen.  
  
-   Inspect.exe ist eine [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)] -Anwendung, die verwendet werden kann, zum Sammeln von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Informationen für Anbieter und Client-Entwicklung und Debuggen. Inspect.exe befindet sich auf die [!INCLUDE[TLA#tla_winfxsdk](../../../includes/tlasharptla-winfxsdk-md.md)].  
  
-   MSAABridge macht [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Informationen für [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Clients verfügbar. Das Hauptziel der Überbrückung zwischen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] und [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] ist, vorhandenen [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Clients die Interaktion mit Frameworks zu ermöglichen, in denen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]implementiert ist.  
  
<a name="Security"></a>   
## <a name="security"></a>Sicherheit  
 Sicherheitsinformationen finden Sie unter [UI Automation Security Overview](../../../docs/framework/ui-automation/ui-automation-security-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/index.md)
