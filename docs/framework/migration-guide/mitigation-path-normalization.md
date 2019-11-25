---
title: 'Entschärfung: Pfadnormalisierung'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 1e7b540975b84320d099ca004df5b6a87aa60f6a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457888"
---
# <a name="mitigation-path-normalization"></a>Entschärfung: Pfadnormalisierung
Ab Apps, die gezielt .NET Framework 4.6.2 verwenden, ändert sich die Pfadnormalisierung in .NET Framework.  
  
## <a name="what-is-path-normalization"></a>Was ist Pfadnormalisierung?  
 Das Normalisieren eines Pfads beinhaltet das Verändern der Zeichenfolge, die einen Pfad oder eine Datei kennzeichnet, in einer Weise, dass sie einem gültigen Pfad im Zielbetriebssystem entspricht. Normalisierung umfasst ist in der Regel:  
  
- Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.  
  
- Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.  
  
- Die Auswertung des relativen Verzeichnisses (`.`) oder des übergeordneten Verzeichnisses (`..`) in einem Pfad.  
  
- Das Verkürzen um angegebene Zeichen.  
  
## <a name="the-changes"></a>Die Änderungen  
 Ab Apps, die gezielt .NET Framework 4.6.2 verwenden, ändert sich die Pfadnormalisierung wie folgt:  
  
- Die Runtime greift auf die Funktion [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) des Betriebssystems zurück, um Pfade zu normalisieren.  
  
- Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).  
  
- Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.  
  
- Die Runtime überprüft Gerätesyntaxpfade nicht.  
  
- Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.  
  
## <a name="impact"></a>Auswirkungen  

Für Apps, die gezielt .NET Framework 4.6.2 oder eine höhere Version verwenden, sind diese Änderungen standardmäßig aktiviert. Sie sollten die Leistung verbessern und Methoden zugleich den Zugriff auf zuvor nicht zugängliche Pfade ermöglichen.  
  
Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.  
  
## <a name="mitigation"></a>Minderung  
 Apps, die gezielt .NET Framework 4.6.2 oder eine höhere Version verwenden, können diese Änderung deaktivieren und die Legacynormalisierung verwenden. Hierzu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei Folgendes hinzugefügt werden:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
Für Apps, die gezielt .NET Framework 4.6.1 oder eine niedrigere Version verwenden, aber unter .NET Framework 4.6.2 oder einer höheren Version ausgeführt werden, können die Änderungen an der Pfadnormalisierung aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
