---
title: WPF-Sicherheitsstrategie – Sicherheitsentwicklung
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
ms.openlocfilehash: 9123d59709b483c72ab49652bda1e547430fa33d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663249"
---
# <a name="wpf-security-strategy---security-engineering"></a>WPF-Sicherheitsstrategie – Sicherheitsentwicklung
Trustworthy Computing ist eine Microsoft-Initiative, die sicherstellen soll, dass sicherer Code entwickelt wird. Ein Schlüsselelement der Trustworthy Computing-Initiative ist der [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)]. Der [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] ist ein Entwicklungsverfahren, das in Verbindung mit standardmäßigen Entwicklungsprozessen verwendet wird, um die Erstellung von sicherem Code zu erleichtern. Der [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] besteht aus zehn Phasen, die bewährte Methoden mit Formalisierung, Messbarkeit und zusätzlichen Strukturen kombinieren, darunter:  
  
- Analyse des Sicherheitsentwurfs  
  
- Qualitätsprüfungen mithilfe von Tools  
  
- Penetrationstests  
  
- Abschließende Sicherheitsüberprüfung  
  
- Verwaltung der Produktsicherheit nach der Veröffentlichung  
  
## <a name="wpf-specifics"></a>WPF im Einzelnen  
 Das [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-Entwicklungsteam wendet den [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] an und ist auch für dessen Erweiterung zuständig; diese Kombination beinhaltet die folgenden Schlüsselaspekte:  
  
 [Erstellen von Gefahrenmodellen](#threat_modeling)  
  
 [Sicherheitsanalyse und Bearbeitungstools](#tools)  
  
 [Testverfahren](#techniques)  
  
 [Verwaltung von sicherheitsrelevantem Code](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a>Erstellen von Gefahrenmodellen  
 Das Erstellen von Gefahrenmodellen ist eine Kernkomponente des [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] und wird zum Erstellen von Systemprofilen verwendet, um potenzielle Sicherheitsanfälligkeiten zu bestimmen. Sobald die Schwachstellen identifiziert sind, kann mithilfe der Gefahrenmodelle zudem sichergestellt werden, dass entsprechende Maßnahmen zur Risikominderung zum Einsatz kommen.  
  
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
 Über die manuellen Elemente der Codesicherheitsprüfung im [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] hinaus verwendet das [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-Team eine Reihe von Tools für die Quellcodeanalyse und die zugeordneten Bearbeitungsschritte, um Sicherheitsschwachstellen zu vermindern. Es wird eine breite Palette von Tools für den Quellcode verwendet, darunter die folgenden:  
  
- **FXCop**: Findet häufige Sicherheitsprobleme in verwaltetem Code von Vererbungsregeln bis hin zu Codeverwendung der zugriffssicherheit zum sicheren Zusammenwirken mit nicht verwaltetem Code. Weitere Informationen finden Sie unter [FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29).  
  
- **Prefix/Prefast**: Findet Schwachstellen des Sicherheit und häufige Sicherheitsprobleme in nicht verwaltetem Code, z. B. Pufferüberläufe, Probleme bei Formatzeichenfolgen von Format und Überprüfung von Fehlern an.  
  
- **Gesperrte APIs**: Durchsucht den Quellcode um die versehentliche Verwendung von Funktionen zu identifizieren, die für Sicherheitsprobleme, z. B. bekannt sind `strcpy`. Nach der Erkennung werden diese Funktionen durch Alternativen ersetzt, die mehr Sicherheit bieten.  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a>Testverfahren  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] verwendet eine Reihe von Techniken zum Testen der Sicherheit, darunter:  
  
- **Whiteboxtests**: Tester Anzeigen von Quellcode und entwickeln dann exploittests  
  
- **Blackboxtests**: Tester versuchen, die zum Suchen Sicherheitsexploits, indem Sie APIs und Funktionen untersuchen und dann versuchen, das Produkt anzugreifen.  
  
- **Zurückverfolgen von Sicherheitsproblemen anderer Produkte**: Sofern Sie relevant sind, werden Sicherheitsprobleme von verwandten Produkten getestet. Beispielsweise wurden entsprechende Varianten von nahezu 60 Sicherheitsproblemen bei [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] erkannt und auf ihre Gültigkeit für [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] hin überprüft.  
  
- **Toolbasierte Penetrationstests durch Dateitests testen**: Datei-fuzzing ist, dass die Ausnutzung eines dateilesemodulen durch eine Vielzahl von Eingaben zur Eingabe gehört. Ein Beispiel, wo diese Technik in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] verwendet wird, besteht in der Prüfung von Code zur Bildentschlüsselung auf Fehler.  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a>Verwaltung von sicherheitsrelevantem Code  
 Für [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] erstellt eine Sicherheitssandbox mithilfe von .NET Framework-Unterstützung für das kennzeichnen und Nachverfolgen von sicherheitskritischem Code, der Berechtigungen heraufstuft (siehe **sicherheitsrelevante Methode** in [WPF -Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)). Angesichts der hohen Qualitätsanforderungen bei sicherheitskritischem Code wird derartiger Code durch eine zusätzliche Ebene der Quellcodeverwaltung und Sicherheitsüberwachung geschützt. Annähernd 5 % bis 10 % von [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] bestehen aus sicherheitskritischem Code, der von einem dedizierten Team überprüft wird. Der Quellcode und der Eincheckvorgang werden verwaltet, indem sicherheitskritischer Code nachverfolgt und jede kritischen Entität (d. h. eine Methode, die kritischen Code enthält) ihrem abgezeichneten Zustand zugeordnet wird. Der abgezeichnete Zustand schließt die Namen eines oder mehrerer Prüfer ein. Bei jedem täglichen Build von [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] wird der kritische Code mit dem in vorhergehenden Builds verglichen, um nicht genehmigte Änderungen aufzuspüren. Wenn ein Programmierer kritischen Code ohne Genehmigung des Prüferteams ändert, wird der betreffende Code erkannt und sofort ersetzt. Dieses Vorgehen ermöglicht die Anwendung und Aufrechterhaltung eines sehr hohen Maßes an Genauigkeit bei [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-Sandboxcode.  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheit](security-wpf.md)
- [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)
- [Trustworthy Computing](https://www.microsoft.com/mscorp/twc/default.mspx)
- [Sicherheit in .NET](../../standard/security/index.md)
