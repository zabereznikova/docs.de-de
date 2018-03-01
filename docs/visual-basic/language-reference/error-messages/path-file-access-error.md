---
title: Pfad-Dateizugriffsfehler
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a>Pfad-/Dateizugriffsfehler
Während eines Datei- oder Datenträgerzugriffs womöglich des Betriebssystems eine Verbindung zwischen den Pfad und den Dateinamen nicht.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Dateispezifikation korrekt formatiert sind. Ein Dateiname darf einen vollqualifizierten (absoluten) oder einen relativen Pfad. Ein vollständig qualifizierter Pfad beginnt mit dem Namen des Laufwerks (falls der Pfad auf einem anderen Laufwerk ist) und den expliziten Pfad vom Stamm der Datei aufgelistet. Alle nicht vollqualifiziert ist Pfad ist relativ zum aktuellen Laufwerks und des Verzeichnisses.  
  
2.  Stellen Sie sicher, dass Sie nicht versuchen, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzen würde. Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei oder speichern Sie die Datei mit einem anderen Dateinamen.  
  
3.  Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei in sequenziellen `Output` oder `Append` Modus. Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus, oder ändern Sie das Schreibschutzattribut der Datei.  
  
4.  Stellen Sie sicher, dass Sie wurde nicht versucht, so ändern Sie eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Projekt innerhalb einer Datenbank oder das Dokument.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
