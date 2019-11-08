---
title: Übersicht über die Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, overview
- user interface, see UI
- accessibility, UI automation
ms.assetid: 65847654-9994-4a9e-b36d-2dd5d998770b
ms.openlocfilehash: d803bd053acd876b3a38cfc52eb29818219e9423
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739585"
---
# <a name="ui-automation-overview"></a>Übersicht über die Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] ist das neue Barrierefreiheits Framework für Microsoft Windows, das auf allen Betriebssystemen verfügbar ist, die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]unterstützen.  
  
 Die[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stellt programmgesteuerten Zugriff auf die meisten [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] auf dem Desktop zur Verfügung, sodass Hilfstechnologieprodukte, z. B. die Bildschirmsprachausgabe, Informationen über die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] für die Endbenutzer bereitstellen und die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mit anderen Verfahren als Standardeingaben ändern können. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht außerdem die Interaktion von automatisierten Testskripts mit der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht keine Kommunikation zwischen Prozessen, die von anderen Benutzern durch den Befehl **Ausführen als** gestartet werden.  
  
 Benutzeroberflächenautomatisierungs-Clientanwendungen können mit der Gewissheit geschrieben werden, dass sie mit verschiedenen Frameworks funktionieren. Der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kern maskiert alle Unterschiede in den Frameworks, die den verschiedenen Komponenten von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]zugrunde liegen. Beispielsweise sind die `Content` -Eigenschaft einer [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Schaltfläche, die `Caption` -Eigenschaft einer [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Schaltfläche und die `ALT` -Eigenschaft eines HTML-Bildes alle nur einer einzelnen Eigenschaft, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>, in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ansicht zugewiesen.  
  
Die Benutzeroberflächen Automatisierung bietet vollständige Funktionalität für unterstützte Windows-Betriebssysteme, auf denen die .NET Framework ausgeführt wird (siehe [.NET Framework Systemanforderungen](../get-started/system-requirements.md) oder Versionen von .net Core ab .net Core 3,0.  
  
 Benutzeroberflächenautomatisierungs-Anbieter bieten durch einen integrierten Überbrückungs Dienst Unterstützung für Microsoft Active Accessibility-Client Anwendungen.  
  
<a name="Providers_and_Clients"></a>   
## <a name="providers-and-clients"></a>Anbieter und Clients  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] verfügt über vier Hauptkomponenten, wie in der folgenden Tabelle aufgeführt.  
  
|Komponente|Beschreibung|  
|---------------|-----------------|  
|Anbieter-API (UIAutomationProvider. dll und UIAutomationTypes. dll)|Eine Reihe von Schnittstellendefinitionen, die von Benutzeroberflächenautomatisierungs-Anbietern implementiert werden, sowie Objekte, die Informationen über [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente bereitstellen und auf Programmeingaben reagieren.|  
|Client-API (UIAutomationClient.dll und UIAutomationTypes.dll)|Eine Reihe von Typen für verwalteten Code, der es Benutzeroberflächenautomatisierungs-Clientanwendungen ermöglicht, Informationen über [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] abzurufen und Eingaben an Steuerelemente zu senden.|  
|UiAutomationCore.dll|Der zugrunde liegende Code (gelegentlich als [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Code bezeichnet), der die Kommunikation zwischen Anbietern und Clients verwaltet.|  
|UIAutomationClientsideProviders.dll|Ein Satz von Benutzeroberflächenautomatisierungs-Anbietern für Standard-Legacysteuerelemente. ([!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente verfügen über systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].) Diese Unterstützung ist für Client Anwendungen automatisch verfügbar.|  
  
 Aus Sicht des Softwareentwicklers gibt es zwei Möglichkeiten zum Verwenden von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: entweder kann eine Unterstützung für benutzerdefinierte Steuerelemente mithilfe der Anbieter-API erstellt werden oder Anwendungen, die den [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kern verwenden, um mit [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elementen mithilfe der Client-API zu kommunizieren. Abhängig von Ihren Schwerpunkten sollten Sie auf verschiedene Teile der Dokumentation zugreifen. In den folgenden Abschnitten können Sie mehr über die Konzepte erfahren und sich praktisches Wissen aneignen.  
  
|Bereich|Inhalt|Zielgruppe|  
|-------------|--------------------|--------------|  
|[Grundlagen der Benutzeroberflächen Automatisierung](index.md) (dieser Abschnitt)|Allgemeine Übersichten über die Konzepte.|Alle|  
|[Benutzeroberflächenautomatisierungs-Anbieter für verwalteten Code](ui-automation-providers-for-managed-code.md)|Übersichten und Hilfethemen zum Verwenden der Anbieter-API.|Entwickler von Steuerelementen.|  
|[Benutzeroberflächenautomatisierungs-Clients für verwalteten Code](ui-automation-clients-for-managed-code.md)|Übersichten und Hilfethemen zum Verwenden der Client-API.|Entwickler von Clientanwendungen.|  
|[Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns.md)|Informationen zum Implementieren von Steuerelementmustern durch Anbieter und den Funktionalitäten, die Clients zur Verfügung stehen.|Alle|  
|[Textmuster zur Benutzeroberflächenautomatisierung](ui-automation-text-pattern.md)|Informationen zum Implementieren des Text-Steuerelementmusters durch Anbieter und den Funktionalitäten, die Clients zur Verfügung stehen.|Alle|  
|[Steuerelementtypen der Benutzeroberflächenautomatisierung](ui-automation-control-types.md)|Informationen über die Eigenschaften und Steuerelementmuster, die von verschiedenen Steuerelementtypen unterstützt werden.|Alle|  
  
 In der folgenden Tabelle werden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Namespaces, die DLLs, die sie enthalten, und die sie verwendende Zielgruppe, aufgelistet.  
  
|Namespace|DLLs, auf die verwiesen wird|Zielgruppe|  
|---------------|---------------------|--------------|  
|<xref:System.Windows.Automation>|UIAutomationClientUIAutomationTypes|Benutzeroberflächenautomatisierungs-Cliententwickler: wird zum Suchen nach <xref:System.Windows.Automation.AutomationElement> -Objekten, zum Registrieren von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignissen und zum Arbeiten mit [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmustern verwendet.|  
|<xref:System.Windows.Automation.Provider>|UIAutomationProviderUIAutomationTypes|Entwickler von Benutzeroberflächenautomatisierungs-Anbietern für andere Frameworks als [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Windows.Automation.Text>|UIAutomationClientUIAutomationTypes|Entwickler von Benutzeroberflächenautomatisierungs-Anbietern für Frameworks, die über [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]hinausgehen. Dieser wird zum Implementieren von TextPattern-Steuerelementmustern verwendet.|  
|<xref:System.Windows.Automation.Peers>|PresentationFramework|Entwickler von Benutzeroberflächenautomatisierungs-Anbietern für [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
  
<a name="UI_Automation_Model"></a>   
## <a name="ui-automation-model"></a>Benutzeroberflächenautomatisierungs-Modell  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] macht [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente für Clientanwendungen vollständig als <xref:System.Windows.Automation.AutomationElement>verfügbar. Elemente sind in einer Baumstruktur, mit dem Desktop als Stammelement, enthalten. Clients können die „Rohdatenansicht“ der Struktur als „Steuerelementansicht“ oder „Inhaltsansicht“ filtern. Anwendungen können auch benutzerdefinierte Ansichten erstellen.  
  
 <xref:System.Windows.Automation.AutomationElement> -Objekte machen allgemeine Eigenschaften der von ihnen dargestellten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente verfügbar. Eine dieser Eigenschaften ist der „Steuerelementtyp“, der die grundlegende Darstellung und Funktionalität als einzelne Entität definiert, z. B. als Schaltfläche oder Kontrollkästchen.  
  
 Darüber hinaus machen Elemente Steuerelementmuster verfügbar, die ihren Steuerelementtypen entsprechende Eigenschaften bereitstellen. Steuerelementmuster machen gleichzeitig Methoden verfügbar, die es Clients ermöglichen, weitere Informationen über das Element zu erlangen und Eingaben bereitzustellen.  
  
> [!NOTE]
> Es gibt keine 1:1-Entsprechung zwischen Steuerelementtypen und Steuerelementmustern. Ein Steuerelementmuster kann von mehreren Steuerelementtypen unterstützt werden, und ein Steuerelement kann mehrere Steuerelementmuster unterstützen, von denen jedes einen anderen Aspekt des Verhaltens verfügbar macht. Ein Kombinationsfeld hat beispielsweise mindestens zwei Steuerelementmuster: eines mit der Fähigkeit zum Erweitern und Reduzieren und ein anderes, das den Auswahlmechanismus darstellt. Weitere Informationen finden Sie unter [UI Automation Control Types](ui-automation-control-types.md).  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gibt durch Ereignisse Informationen an Clientanwendungen weiter. Im Gegensatz zu WinEvents basieren [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ereignisse nicht auf einem Übertragungsmechanismus. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Clients melden sich für bestimmte Ereignisbenachrichtigungen an und können anfordern, dass spezifische [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften und Steuerelementmuster-Informationen an den Ereignishandler übergeben werden. Außerdem enthält ein [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis einen Verweis auf das Element, das es ausgelöst hat. Anbieter können die Leistung verbessern, indem sie Ereignisse selektiv abhängig davon auslösen, ob Clients zuhören.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften](ui-automation-properties-overview.md)
- [Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse](ui-automation-events-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit](ui-automation-security-overview.md)
