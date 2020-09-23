---
title: Ungültige Datensatznummer
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 8cbffc7714211fb10bedc3a73729eac59d98f0bb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086984"
---
# <a name="bad-record-number"></a>Ungültige Datensatznummer

Die Datensatznummer in der `a FileGet`, `FilePut`, `FileGetObject`oder `FilePutObject` -Anweisung ist kleiner oder gleich 0 (null).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die zum Generieren der Datensatznummer verwendeten Berechnungen. Überprüfen Sie die Rechtschreibung der Variablen, die die Datensatznummer enthalten oder bei der Berechnung von Datensatznummern verwendet werden. Ein falsch geschriebener Variablenname wird implizit deklariert und zu 0 (null) initialisiert, es sei denn, Sie haben `Option Explicit On` im Modul verwendet.  
  
## <a name="see-also"></a>Siehe auch

- [Option Explicit-Anweisung](../language-reference/statements/option-explicit-statement.md)
