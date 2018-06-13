---
title: Pfad-Dateizugriffsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 83ce8615b173a6f5835347ebc561a793655ec8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598582"
---
# <a name="pathfile-access-error"></a>Pfad-/Dateizugriffsfehler
Während eines Datei- oder Datenträgerzugriffs womöglich des Betriebssystems eine Verbindung zwischen den Pfad und den Dateinamen nicht.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Dateispezifikation korrekt formatiert sind. Ein Dateiname darf einen vollqualifizierten (absoluten) oder einen relativen Pfad. Ein vollständig qualifizierter Pfad beginnt mit dem Namen des Laufwerks (falls der Pfad auf einem anderen Laufwerk ist) und den expliziten Pfad vom Stamm der Datei aufgelistet. Alle nicht vollqualifiziert ist Pfad ist relativ zum aktuellen Laufwerks und des Verzeichnisses.  
  
2.  Stellen Sie sicher, dass Sie nicht versuchen, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzen würde. Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei oder speichern Sie die Datei mit einem anderen Dateinamen.  
  
3.  Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei in sequenziellen `Output` oder `Append` Modus. Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus, oder ändern Sie das Schreibschutzattribut der Datei.  
  
4.  Stellen Sie sicher, dass Sie nicht versuchen, ein Visual Basic-Projekt in einer Datenbank oder das Dokument zu ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
