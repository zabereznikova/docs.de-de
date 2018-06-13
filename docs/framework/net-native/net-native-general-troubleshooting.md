---
title: .NET Native Allgemeine Problembehandlung
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b53150c90e473e7c4ed32991c43ff0b8ca5b75b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396284"
---
# <a name="net-native-general-troubleshooting"></a>.NET Native Allgemeine Problembehandlung
Dieses Thema beschreibt die Behandlung möglicher Probleme, die bei der Entwicklung von Apps mit [!INCLUDE[net_native](../../../includes/net-native-md.md)] auftreten können.  
  
-   **Problem:** Das Buildausgabefenster wird nicht ordnungsgemäß aktualisiert.  
  
     **Lösung:** Das Buildausgabefenster wird erst aktualisiert, wenn der Build abgeschlossen ist. Buildzeiten können bis zu mehreren Minuten dauern, daher kann eine Verzögerung bei der Aktualisierung der Anzeige auftreten.  
  
-   **Problem:** Die Buildzeit der Verkaufsversion Ihrer App für ARM hat zugenommen.  
  
     **Lösung:** Beim Bereitstellen einer App auf Ihrem ARM-Gerät wird die [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Infrastruktur aufgerufen. Bei dieser Kompilierung wird eine große Anzahl von Optimierungen ausgeführt und gleichzeitig sichergestellt, dass nicht statische Semantik, wie Reflektion, weiterhin funktioniert. Darüber hinaus wird der Teil von .NET Framework, den die App verwendet, für optimale Leistung statisch eingebunden und muss ebenfalls in systemeigenen Code kompiliert werden. Deshalb dauert die Kompilierung länger.  
  
     Allerdings liegen die Kompilierungszeiten für die meisten Apps auf einem Standardentwicklungscomputer bei Standardkompilierung noch innerhalb einer Minute.  Nur das Generieren von systemeigenen Images für .NET Framework auf einem Standardentwicklungscomputer dauert in der Regel mehrere Minuten.  Sogar mit allen Optimierungen zur Verbesserung des generierten Codes und mit Einschließen von .NET Framework liegen die Buildzeiten von Apps in der Regel bei ein oder zwei Minuten.  
  
     Wir arbeiten weiterhin an der Verbesserung der Kompilierungsleistung, indem wir Multithreadkompilierung und andere Optimierungen untersuchen.  
  
-   **Problem:** Sie sind sich nicht sicher, ob Ihre App mit [!INCLUDE[net_native](../../../includes/net-native-md.md)] kompiliert wurde.  
  
     **Lösung:** Wenn der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler aufgerufen wird, werden Sie längere Buildzeiten feststellen, und der Task-Manager zeigt verschiedene [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Prozesse wie „ILC.exe“ und „nutc_driver.exe“ an.  
  
     Nachdem Sie Ihr Projekt erfolgreich mit [!INCLUDE[net_native](../../../includes/net-native-md.md)] erstellt haben, finden Sie die Ausgabe unter „obj\\*config*\ *arch*\\*projectname*.ilc\out“.  Der endgültige native Paketinhalt befindet sich unter „bin\\*arch*\\*config*\AppX“. Der endgültige native Paketinhalt steht unter „\bin\\*arch*\\*config*\AppX“, wenn Sie die App bereitgestellt haben.  
  
-   **Problem:** Die mit .NET Native kompilierte App löst Laufzeitausnahmen aus (in der Regel [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)- oder [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)-Ausnahmen), die beim Kompilieren ohne .NET Native nicht ausgelöst wurden.  
  
     **Lösung:** Die Ausnahmen werden ausgelöst, da .NET Native weder Metadaten noch Implementierungscode bereitstellt, die andernfalls durch Reflektion verfügbar sind. (Weitere Informationen finden Sie unter [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md).) Zur Beseitigung dieser Ausnahme müssen Sie Ihrer [Laufzeitanweisungsdatei (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) einen Eintrag hinzufügen, damit die .NET Native-Toolkette die Metadaten oder den Implementierungscode zur Laufzeit bereitstellen kann. Es sind zwei Problembehandlungen verfügbar, die den entsprechenden Eintrag für die Laufzeitanweisungsdatei zur Beseitigung der Ausnahme generieren:  
  
    -   Die [MissingMetadataException-Problembehandlung](http://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
  
    -   Die [MissingMetadataException-Problembehandlung](http://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
     Weitere Informationen finden Sie unter [Reflektion und .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Migrieren der Windows Store-App zu .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
