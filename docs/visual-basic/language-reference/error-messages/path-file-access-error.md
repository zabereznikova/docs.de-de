---
title: Pfad-Dateizugriffsfehler | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ac730bac76540331206daebe600445ca54cc15a9
ms.lasthandoff: 03/13/2017

---
# <a name="pathfile-access-error"></a>Pfad-/Dateizugriffsfehler
Während eines Datei- oder Datenträgerzugriffs konnte das Betriebssystem eine Verbindung zwischen dem Pfad und der Dateiname nicht auszuführen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Dateispezifikation richtig formatiert ist. Ein Dateiname darf einen vollqualifizierten (absoluten) oder ein relativer Pfad. Ein vollqualifizierter Pfad beginnt mit dem Laufwerknamen (falls der Pfad auf einem anderen Laufwerk ist) und listet den expliziten Pfad vom Stammelement der Datei. Alle, die nicht den vollqualifizierten Pfad ist relativ zum aktuellen Laufwerk und Verzeichnis.  
  
2.  Stellen Sie sicher, dass Sie nicht versuchen, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzen möchten. Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei, oder speichern Sie die Datei mit einem anderen Dateinamen.  
  
3.  Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei im sequenziellen`Output`oder `Append` Modus. Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus oder ändern Sie das Schreibschutzattribut der Datei.  
  
4.  Stellen Sie sicher, dass Sie nicht versucht haben, ändern Sie ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekt innerhalb einer Datenbank oder eines Dokuments.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
