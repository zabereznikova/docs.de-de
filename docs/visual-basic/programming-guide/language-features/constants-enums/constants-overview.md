---
title: Übersicht über Konstanten (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40330e8c2c60c866200e009a8280c7ec9c855435
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="constants-overview-visual-basic"></a>Übersicht über Konstanten (Visual Basic)
Eine Konstante ist, einen aussagekräftigen Namen, der anstelle einer Zahl oder eine Zeichenfolge, die nicht geändert wird. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung unverändert bleiben. Sie können erheblich verbessern die Lesbarkeit des Codes und stellen die einfacher zu verwalten, bei dem Konstanten. In Code, der Werte enthält, die wieder zu verwenden, oder, abhängig ist, bestimmte Zahlen, die schwer zu merken, oder keine offensichtliche Bedeutung haben.  
  
## <a name="how-to-create-and-use-constants"></a>Gewusst wie: Erstellen und Verwenden von Konstanten  
 Visual Basic enthält eine Reihe vordefinierter Konstanten mit hauptsächlich zum Drucken und anzeigen. Sie können auch eigene Konstanten mit Erstellen der `Const` verwenden Sie dieselben Richtlinien zum Erstellen eines Variablennamens-Anweisung. Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.  
  
 Der Gültigkeitsbereich einer Konstanten, d. h. die Menge des gesamten Codes, die darauf verweisen kann, ohne dessen Namen zu qualifizieren, ist dieselbe wie eine Variable deklariert, die am gleichen Speicherort. Um eine Konstante zu erstellen, die innerhalb des Bereichs einer bestimmten Prozedur vorhanden ist, deklarieren Sie es in dieser Prozedur aus. Um eine Konstante zu erstellen, die innerhalb der gesamten Anwendung verfügbar ist, deklarieren Sie sie mithilfe der `Public` Schlüsselwort im Deklarationsabschnitt der Klasse.  
  
> [!NOTE]
>  Obwohl Konstanten etwas Variablen ähneln, nicht ändern, oder weisen wie Variablen Sie können neue Werte zu werden.  
  
 Die Konstanten, die Sie in Ihrem Code verwenden, können das Objektmodell für Steuerelemente oder Komponenten definiert werden, oder sie können eine benutzerdefinierte (d. h., die Sie selbst erstellen).  
  
## <a name="compile-time-and-run-time-constants"></a>Zeitpunkt der Kompilierung und Laufzeit-Konstanten  
 Zum Zeitpunkt, den der Code kompiliert wird, während eine Konstante zur Laufzeit nur ermittelt werden kann, während die Anwendung ausgeführt wird, wird eine Kompilierzeitkonstante berechnet. Eine Kompilierzeitkonstante, den gleichen Wert jedes Mal haben, die eine Anwendung ausgeführt wird, während eine Konstante zur Laufzeit jedes Mal ändern kann. Kompilierungszeitskonstanten sind für Fälle, z. B. Arraygrenzen, Case-Ausdrücke oder Enumerator Initialisierer erforderlich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Definition|Begriff|  
|---|---|  
|[Gewusst wie: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Erklärt, wie die `Const` -Anweisung zum Deklarieren einer Konstante mit dem Wert; durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen, mit dem Wert.|  
|[Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Beschreibt, wie Ihre eigenen Konstanten, einschließlich Informationen über den Bereichsdefinition erstellt und wie, Zirkelverweise zu vermeiden.|  
|[Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Enthält Informationen wie die Visual Basic-Compiler Konstanten initialisiert, wenn `Option Explicit` ist deaktiviert.|  
|[Gewusst wie: Gruppieren verwandter konstanter Werte](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Veranschaulicht, wie Konstante Werte gruppiert, die verknüpft sind.|  
  
## <a name="reference"></a>Referenz  
  
|Definition|Begriff|  
|---|---|  
|[Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Enthält die Konstanten, die vom Visual Basic vordefiniert.|  
|[Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)|Beschreibt die `Const` -Anweisung und dessen Verwendung.|  
|[Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Beschreibt die `Option Strict` -Anweisung und dessen Verwendung.|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)
