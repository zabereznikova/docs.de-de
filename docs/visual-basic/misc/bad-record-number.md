---
title: Ungültige Datensatznummer
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: fbf1a2db97d0474fb758ff5ed572e94395a187da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664751"
---
# <a name="bad-record-number"></a>Ungültige Datensatznummer
Die Datensatznummer in der `a FileGet`, `FilePut`, `FileGetObject`oder `FilePutObject` -Anweisung ist kleiner oder gleich 0 (null).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die zum Generieren der Datensatznummer verwendeten Berechnungen. Überprüfen Sie die Rechtschreibung der Variablen, die die Datensatznummer enthalten oder bei der Berechnung von Datensatznummern verwendet werden. Ein falsch geschriebener Variablenname wird implizit deklariert und zu 0 (null) initialisiert, es sei denn, Sie haben `Option Explicit On` im Modul verwendet.  
  
## <a name="see-also"></a>Siehe auch
- [Option Explicit-Anweisung](../../visual-basic/language-reference/statements/option-explicit-statement.md)
