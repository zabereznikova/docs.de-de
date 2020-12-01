---
title: 'Entschärfung: Pfadnormalisierung'
description: In diesem Artikel erfahren Sie, welche Veränderungen sich bei der Pfadnormalisierung in Apps ergeben, die auf .NET Framework 4.6.2 oder höher ausgerichtet sind.
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 6f7e07690ab06fc7ef03344556c045405a63c374
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253595"
---
# <a name="mitigation-path-normalization"></a>Entschärfung: Pfadnormalisierung

Bei Apps, die für .NET Framework 4.6.2 oder höher entwickelt wurden, ergeben sich Änderungen bei der Pfadnormalisierung im .NET Framework.  
  
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

 In Apps, die für .NET Framework 4.6.2 oder höher entwickelt wurden, kann diese Änderung deaktiviert und die Legacynormalisierung verwendet werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei Folgendes hinzugefügt werden:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
In Apps, die auf .NET Framework 4.6.1 oder niedriger ausgerichtet sind, aber unter .NET Framework 4.6.2 oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
