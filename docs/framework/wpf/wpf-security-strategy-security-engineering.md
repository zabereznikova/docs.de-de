---
title: Sicherheitsstrategie und Engineering
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: 57ee0c8242c0bca1b2c76e7751ed25f6a889c264
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741836"
---
# <a name="wpf-security-strategy---security-engineering"></a>WPF-Sicherheitsstrategie – Sicherheitsentwicklung
Trustworthy Computing ist eine Microsoft-Initiative, die sicherstellen soll, dass sicherer Code entwickelt wird. Ein wichtiges Element der Initiative zum vertrauenswürdigen Computing ist die Microsoft Security Development Lifecycle (SDL). Die SDL ist eine Engineering-Übung, die in Verbindung mit standardmäßigen Entwicklungsprozessen verwendet wird, um die Bereitstellung von sicherem Code zu vereinfachen. Das SDL besteht aus zehn Phasen, die bewährte Methoden mit Formalisierung, Measurability und zusätzlicher Struktur kombinieren, einschließlich:  
  
- Analyse des Sicherheitsentwurfs  
  
- Qualitätsprüfungen mithilfe von Tools  
  
- Penetrationstests  
  
- Abschließende Sicherheitsüberprüfung  
  
- Verwaltung der Produktsicherheit nach der Veröffentlichung  
  
## <a name="wpf-specifics"></a>WPF im Einzelnen  
 Das [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Engineering-Team wendet das SDL an und erweitert es. die Kombination von umfasst die folgenden wichtigen Aspekte:  
  
 [Erstellen von Gefahrenmodellen](#threat_modeling)  
  
 [Sicherheitsanalyse und Bearbeitungstools](#tools)  
  
 [Testverfahren](#techniques)  
  
 [Verwaltung von sicherheitsrelevantem Code](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a>Erstellen von Gefahrenmodellen  
 Die Bedrohungsmodellierung ist eine Kernkomponente von SDL und wird zum Erstellen eines Profils für ein System verwendet, um potenzielle Sicherheitsrisiken zu ermitteln. Sobald die Schwachstellen identifiziert sind, kann mithilfe der Gefahrenmodelle zudem sichergestellt werden, dass entsprechende Maßnahmen zur Risikominderung zum Einsatz kommen.  
  
 Im Überblick umfasst die Erstellung von Gefahrenmodellen die folgenden Hauptschritte, hier am Beispiel eines Lebensmittelmarkts verdeutlicht:  
  
1. **Ressourcenermittlung**. Zu den Ressourcen eines Lebensmittelmarkts können etwa die Mitarbeiter, ein Tresor, Registrierkassen und der Warenbestand gehören.  
  
2. **Aufzählen der Einstiegspunkte**. Die Einstiegspunkte eines Lebensmittelmarkts können etwa die Vorder- und Hintertüren, Fenster, das Ladedeck und die Öffnungen der Klimaanlage zählen.  
  
3. **Untersuchen von Angriffen auf Ressourcen mithilfe der Einstiegspunkte**. Ein mögliches Angriffsszenario könnte auf die Ressource *Tresor* des Lebensmittelmarkts über den Einstiegspunkt *Öffnungen der Klimaanlage* abzielen; die Klimaanlage könnte demontiert werden, um das Herausziehen des Tresors aus dem Lebensmittelmarkt durch die Lüftungsschächte zu ermöglichen.  
  
 Die Erstellung von Gefahrenmodellen wird in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] durchgängig angewendet und schließt folgende Punkte ein:  
  
- Die Weise, in der der [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]-Parser Dateien liest, Text zu entsprechenden Objektmodellklassen zuordnet und den tatsächlichen Code erstellt.  
  
- Wie ein Fensterhandle (hWnd) erstellt wird, Nachrichten sendet und zum Rendern der Inhalte eines Fensters verwendet wird.  
  
- Wie die Datenbindung Ressourcen erhält und mit dem System interagiert.  
  
 Diese Gefahrenmodelle sind wichtig, um die Anforderungen an den Sicherheitsentwurf und die Maßnahmen der Gefahrenabwehr während des Entwicklungsprozesses zu bestimmen.  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a>Quellcodeanalyse und Bearbeitungstools  
 Zusätzlich zu den manuellen Sicherheits Code Review Elementen der SDL verwendet das [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Team mehrere Tools für die Quell Analyse und zugehörige Änderungen, um Sicherheitsrisiken zu verringern. Es wird eine breite Palette von Tools für den Quellcode verwendet, darunter die folgenden:  
  
- **FXCop**: Findet häufige Sicherheitsprobleme in verwaltetem Code, beginnend mit Vererbungsregeln über die Verwendung der Zugriffssicherheit im Code bis hin zum sicheren Zusammenwirken mit nicht verwaltetem Code. Weitere Informationen finden Sie unter [FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29).  
  
- **Prefix/Prefast**: Findet Schwachstellen des Sicherheit und häufige Sicherheitsprobleme in nicht verwaltetem Code, wie etwa Pufferüberläufe, Probleme bei Formatzeichenfolgen und Fehlerprüfung.  
  
- **Gesperrte APIs**: Durchsucht den Quellcode, um die versehentliche Verwendung von Funktionen zu erkennen, die für Sicherheitsprobleme bekannt sind, wie etwa `strcpy`. Nach der Identifizierung werden diese Funktionen durch Alternativen ersetzt, die sicherer sind.  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a>Testverfahren  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] verwendet eine Reihe von Techniken zum Testen der Sicherheit, darunter:  
  
- **Whiteboxtests**: Tester zeigen Quellcode an und erstellen dann exploittests.
  
- **Blackboxtests**: Tester suchen Sicherheitsexploits, indem Sie APIs und Funktionen untersuchen und dann versuchen, das Produkt anzugreifen.  
  
- **Zurückverfolgen von Sicherheitsproblemen anderer Produkte**: Sofern sie relevant sind, werden Sicherheitsprobleme von verwandten Produkten getestet. Beispielsweise wurden entsprechende Varianten von ungefähr 60 Sicherheitsproblemen für Internet Explorer identifiziert, und es wurde versucht, ihre Anwendbarkeit zu [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].  
  
- **Toolbasierte Penetrationstests durch Dateitests mit zufälligen Daten**: Dateitests mit zufälligen Daten stellen die Ausnutzung des Eingabebereichs von Dateilesemodulen durch eine Vielzahl von Eingaben dar. Ein Beispiel, wo diese Technik in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] verwendet wird, besteht in der Prüfung von Code zur Bildentschlüsselung auf Fehler.  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a>Verwaltung von sicherheitsrelevantem Code  
 Bei XAML-Browser Anwendungen (XBAPs) erstellt [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] eine Sicherheits Sandbox mithilfe .NET Framework Unterstützung für das Markieren und Nachverfolgen von Sicherheits kritischem Code, der Berechtigungen erhöht (siehe **sicherheitskritische Methodik** in [WPF-Sicherheitsstrategie-Plattformsicherheit](wpf-security-strategy-platform-security.md)). Angesichts der hohen Qualitätsanforderungen bei sicherheitskritischem Code wird derartiger Code durch eine zusätzliche Ebene der Quellcodeverwaltung und Sicherheitsüberwachung geschützt. Annähernd 5 % bis 10 % von [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] bestehen aus sicherheitskritischem Code, der von einem dedizierten Team überprüft wird. Der Quellcode und der Eincheckvorgang werden verwaltet, indem sicherheitskritischer Code nachverfolgt und jede kritischen Entität (d. h. eine Methode, die kritischen Code enthält) ihrem abgezeichneten Zustand zugeordnet wird. Der abgezeichnete Zustand schließt die Namen eines oder mehrerer Prüfer ein. Bei jedem täglichen Build von [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] wird der kritische Code mit dem in vorhergehenden Builds verglichen, um nicht genehmigte Änderungen aufzuspüren. Wenn ein Programmierer kritischen Code ohne Genehmigung des Prüferteams ändert, wird der betreffende Code erkannt und sofort ersetzt. Dieses Vorgehen ermöglicht die Anwendung und Aufrechterhaltung eines sehr hohen Maßes an Genauigkeit bei [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-Sandboxcode.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheit](security-wpf.md)
- [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)
- [Vertrauenswürdiges Computing](https://www.microsoft.com/mscorp/twc/default.mspx)
- [Sicherheit in .NET](../../standard/security/index.md)
