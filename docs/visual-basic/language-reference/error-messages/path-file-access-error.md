---
title: Pfad-/Dateizugriffsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 70de8f9cb33ab3d889f4916ae3d5de48cd218092
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871196"
---
# <a name="pathfile-access-error"></a>Pfad-/Dateizugriffsfehler

Bei einem Datei Zugriffs-oder Datenträger Zugriffs Vorgang konnte das Betriebssystem keine Verbindung zwischen dem Pfad und dem Dateinamen herstellen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass die Datei Spezifikation ordnungsgemäß formatiert ist. Ein Dateiname kann einen voll qualifizierten (absoluten) oder relativen Pfad enthalten. Ein voll qualifizierter Pfad beginnt mit dem Laufwerks Namen (wenn sich der Pfad auf einem anderen Laufwerk befindet) und listet den expliziten Pfad vom Stamm zur Datei auf. Alle Pfade, die nicht voll qualifiziert sind, sind relativ zum aktuellen Laufwerk und Verzeichnis.  
  
2. Stellen Sie sicher, dass Sie nicht versucht haben, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzt. Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei, oder speichern Sie die Datei unter einem anderen Dateinamen.  
  
3. Stellen Sie sicher, dass Sie nicht versucht haben, eine schreibgeschützte Datei in sequenzieller oder-Modus zu öffnen `Output` `Append` . Wenn dies der Fall ist, öffnen Sie die Datei im- `Input` Modus, oder ändern Sie das schreibgeschützte Attribut der Datei.  
  
4. Stellen Sie sicher, dass Sie nicht versucht haben, ein Visual Basic Projekt innerhalb einer Datenbank oder eines Dokuments zu ändern.  
  
## <a name="see-also"></a>Weitere Informationen

- [Fehlertypen](../../programming-guide/language-features/error-types.md)
