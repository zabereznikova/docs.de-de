---
title: Übersicht über Konstanten
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 7f2a2dc140352588246d80a7feb46ce1f609b358
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086282"
---
# <a name="constants-overview-visual-basic"></a>Übersicht über Konstanten (Visual Basic)

Eine Konstante ist ein sinnvoller Name, der den Speicherort einer Zahl oder Zeichenfolge annimmt, der sich nicht ändert. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung gleich bleiben. Sie können die Lesbarkeit des Codes erheblich verbessern und die Verwaltung mithilfe von Konstanten vereinfachen. Verwenden Sie Sie in Code, der Werte enthält, die erneut angezeigt werden oder von bestimmten Zahlen abhängen, die schwer zu merken sind oder die nicht offensichtlich sind.  
  
## <a name="how-to-create-and-use-constants"></a>Erstellen und Verwenden von Konstanten  

 Visual Basic enthält eine Reihe vordefinierter Konstanten, die hauptsächlich zum Drucken und Anzeigen von verwendet werden. Sie können auch eigene Konstanten mit der- `Const` Anweisung erstellen, indem Sie die gleichen Richtlinien verwenden, die Sie zum Erstellen eines Variablen namens verwenden würden. Wenn `Option Strict` ist `On` , müssen Sie den Konstantentyp explizit deklarieren.  
  
 Der Gültigkeitsbereich einer Konstante, bei dem es sich um den Satz des gesamten Codes handelt, der darauf verweisen kann, ohne den Namen zu qualifizieren, entspricht dem Wert einer Variablen, die an derselben Stelle deklariert wurde. Um eine Konstante zu erstellen, die im Bereich einer bestimmten Prozedur vorhanden ist, deklarieren Sie Sie in dieser Prozedur. Zum Erstellen einer Konstanten, die in einer beliebigen Anwendung verfügbar ist, deklarieren Sie Sie mithilfe des- `Public` Schlüssel Worts im Deklarations Abschnitt der-Klasse.  
  
> [!NOTE]
> Obwohl Konstanten in gewisser Weise Variablen ähneln, können Sie Sie nicht ändern oder Ihnen neue Werte wie Variablen zuweisen.  
  
 Die Konstanten, die Sie im Code verwenden, können durch das Objektmodell für Steuerelemente oder Komponenten definiert werden, mit denen Sie arbeiten, oder Sie können Benutzer definiert sein (d. h. diejenigen, die Sie selbst erstellen).  
  
## <a name="compile-time-and-run-time-constants"></a>Kompilierzeit-und Lauf Zeitkonstanten  

 Eine Kompilierzeit Konstante wird zu dem Zeitpunkt berechnet, zu dem der Code kompiliert wird, während eine Lauf Zeitkonstante nur berechnet werden kann, während die Anwendung ausgeführt wird. Eine Kompilierzeit Konstante hat bei jeder Ausführung einer Anwendung denselben Wert, während sich eine Lauf Zeitkonstante jederzeit ändern kann. Kompilierzeit Konstanten sind für Fälle wie Array Begrenzungen, CASE-Ausdrücke oder enumeratorinitialisierer erforderlich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Definition|Begriff|  
|---|---|  
|[Vorgehensweise: Deklarieren einer Konstante](how-to-declare-a-constant.md)|Erläutert, wie die `Const` -Anweisung verwendet wird, um eine Konstante zu deklarieren und ihren Wert festzulegen. durch das Deklarieren einer Konstanten weisen Sie dem Wert einen aussagekräftigen Namen zu.|  
|[Benutzerdefinierte Konstanten](user-defined-constants.md)|Beschreibt, wie Sie Ihre eigenen Konstanten erstellen, einschließlich Informationen zum Bereich und zur Vermeidung von Zirkel verweisen.|  
|[Konstanten und literale Datentypen](constant-and-literal-data-types.md)|Stellt Informationen dazu bereit, wie der Visual Basic Compiler Konstanten initialisiert, wenn deaktiviert `Option Explicit` ist.|  
|[Vorgehensweise: Gruppieren verwandter konstanter Werte](how-to-group-related-constant-values-together.md)|Veranschaulicht das Gruppieren konstanter Werte, die verknüpft sind.|  
  
## <a name="reference"></a>Referenz  
  
|Definition|Begriff|  
|---|---|  
|[Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)|Listet die Konstanten auf, die durch Visual Basic vordefiniert sind.|  
|[Const-Anweisung](../../../language-reference/statements/const-statement.md)|Beschreibt die `Const` -Anweisung und deren Verwendung.|  
|[Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)|Beschreibt die `Option Strict` -Anweisung und deren Verwendung.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Enumerationen](enumerations-overview.md)
- [How to: Initialize an Array Variable in Visual Basic](../arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)
