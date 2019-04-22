---
title: Übersicht über Konstanten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 2939110de77718baf32e2a0d8f1aa52dba997cf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841295"
---
# <a name="constants-overview-visual-basic"></a>Übersicht über Konstanten (Visual Basic)
Eine Konstante ist, einen aussagekräftigen Namen, der nimmt den Platz einer Zahl oder Zeichenfolge, die nicht geändert wird. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung unverändert bleiben. Sie können erheblich verbessern die Lesbarkeit des Codes und erleichtern es, beibehalten, indem Sie die Konstanten. In Code, der Werte enthält, die wieder verwenden, oder das hängt vom bestimmten Zahlen, die schwer zu merken oder keine offensichtliche Bedeutung haben.  
  
## <a name="how-to-create-and-use-constants"></a>Das Erstellen und verwenden Sie Konstanten  
 Visual Basic enthält eine Reihe vordefinierter Konstanten verwenden vor allem zum Drucken und anzeigen. Sie können auch Ihre eigenen Konstanten mit erstellen die `Const` Anweisung, verwenden Sie dieselben Richtlinien für die Erstellung eines Variablennamens. Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.  
  
 Der Gültigkeitsbereich einer Konstanten, die den Satz des gesamten Codes ist, die darauf verweisen können, ohne Angabe ihres Namens, ist identisch mit einer Variablen, die sich am gleichen Standort deklariert. Um eine Konstante zu erstellen, die innerhalb des Bereichs einer bestimmten Prozedur vorhanden ist, deklarieren Sie sie in dieser Prozedur aus. Um eine Konstante zu erstellen, die in der gesamten Anwendung verfügbar ist, deklarieren Sie sie mithilfe der `Public` Schlüsselwort im Deklarationsabschnitt der Klasse.  
  
> [!NOTE]
>  Obwohl Konstanten etwas Variablen ähneln, nicht ändern oder neue Werte zuweisen, wie Sie Variablen können.  
  
 Die Konstanten, die Sie in Ihrem Code verwenden definiert werden, indem das Objektmodell für Steuerelemente oder Komponenten, die Sie mit arbeiten, oder sie können benutzerdefiniert sein (d. h., die Sie selbst erstellen).  
  
## <a name="compile-time-and-run-time-constants"></a>Während der Kompilierung und Laufzeit-Konstanten  
 Eine Kompilierzeitkonstante wird zur Zeit berechnet, die der Code kompiliert wird, obwohl nur eine Konstante zur Laufzeit berechnet werden kann, während die Anwendung ausgeführt wird, ist. Eine Kompilierzeitkonstante liefert den gleichen Wert jedes Mal ist eine Anwendung ausgeführt wird, während eine Konstante zur Laufzeit jedes Mal ändern kann. Kompilierzeitkonstanten sind für Fälle wie Arraygrenzen, Case-Ausdrücke oder Enumerator Initialisierer erforderlich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Definition|Begriff|  
|---|---|  
|[Vorgehensweise: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Erläutert, wie die `Const` Anweisung, um eine Konstante deklariert, und legen Sie dessen Wert; durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen, mit dem Wert.|  
|[Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Beschreibt wie Sie Ihre eigenen Konstanten, die mit Informationen zum Gültigkeitsbereich zu erstellen und um Zirkelverweise zu vermeiden.|  
|[Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Erläutert, wie Visual Basic-Compiler Konstanten initialisiert, wenn `Option Explicit` ist deaktiviert.|  
|[Vorgehensweise: Gruppieren verwandter konstanter Werte](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Veranschaulicht, wie Konstante Werte gruppiert, die verknüpft sind.|  
  
## <a name="reference"></a>Referenz  
  
|Definition|Begriff|  
|---|---|  
|[Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Enthält die Konstanten, die von Visual Basic vordefiniert.|  
|[Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)|Beschreibt die `Const` Anweisung und deren Verwendung.|  
|[Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Beschreibt die `Option Strict` Anweisung und deren Verwendung.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Vorgehensweise: Initialisieren einer Arrayvariablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
