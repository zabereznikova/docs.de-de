---
title: Pfad / Dateizugriffsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 53f021faa9e4ae69a71d825ca823e1180421afc6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522478"
---
# <a name="pathfile-access-error"></a>Pfad-/Dateizugriffsfehler
Während eines Datei- oder Datenträgerzugriffs könnte das Betriebssystem keine Verbindung zwischen dem Pfad und den Dateinamen herstellen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Dateispezifikation richtig formatiert ist. Ein Dateiname darf eine vollqualifizierte (absolut) oder einen Pfad relativ Pfad. Ein vollqualifizierter Pfad beginnt mit den Namen des Laufwerks (wenn der Pfad auf einem anderen Laufwerk) und den expliziten Pfad vom Stamm zu der Datei aufgelistet. Alle, die nicht den vollqualifizierten Pfad ist relativ zu das aktuelle Laufwerk und Verzeichnis.  
  
2.  Stellen Sie sicher, dass Sie nicht versucht haben, zum Speichern einer Datei, die eine vorhandene schreibgeschützte Datei ersetzen. Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei oder speichern Sie die Datei mit einem anderen Dateinamen.  
  
3.  Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei in sequenziellen `Output` oder `Append` Modus. Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus oder ändern Sie das Attribut "schreibgeschützt" der Datei.  
  
4.  Stellen Sie sicher, dass Sie nicht versucht haben, um ein Visual Basic-Projekt in einer Datenbank oder das Dokument zu ändern.  
  
## <a name="see-also"></a>Siehe auch
- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
