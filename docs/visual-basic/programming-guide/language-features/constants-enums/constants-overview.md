---
title: "Übersicht über Konstanten (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
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
ms.openlocfilehash: 8004045d233da0db017b26b350743ad9f8d61845
ms.lasthandoff: 03/13/2017

---
# <a name="constants-overview-visual-basic"></a>Übersicht über Konstanten (Visual Basic)
Eine Konstante ist ein aussagekräftiger Name, der anstelle einer Zahl oder Zeichenfolge, die nicht geändert werden. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung unverändert bleiben. Sie können erheblich verbessern die Lesbarkeit des Codes und zu verwalten, indem Sie mithilfe von Konstanten erleichtern. In Code, der Werte enthält, die wieder verwenden oder das hängt vom bestimmte Zahlen, die schwer zu merken oder keine offensichtliche Bedeutung haben.  
  
## <a name="how-to-create-and-use-constants"></a>Gewusst wie: Erstellen und Verwenden von Konstanten  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]enthält eine Reihe von vordefinierten Konstanten, die hauptsächlich zum Drucken und anzeigen. Sie können auch Ihre eigenen Konstanten durch Erstellen der `Const` Anweisung, verwenden Sie dieselben Richtlinien für die Erstellung eines Variablennamens. Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.  
  
 Der Gültigkeitsbereich einer Konstanten, die den Satz des gesamten Codes auf sie verweisen können, ohne dessen Namen zu qualifizieren, ist eine Variable, die am gleichen Speicherort identisch. Um eine Konstante zu erstellen, die im Rahmen einer bestimmten Prozedur vorhanden ist, deklarieren sie innerhalb der Prozedur. Um eine Konstante zu erstellen, die innerhalb der gesamten Anwendung verfügbar ist, deklarieren Sie sie mithilfe der `Public` -Schlüsselwort in der Sie im Deklarationsabschnitt der Klasse.  
  
> [!NOTE]
>  Obwohl Konstanten etwas Variablen ähneln, nicht ändern oder neue Werte zuordnen wie Variablen.  
  
 Die Konstanten, die Sie in Ihrem Code verwenden, können das Objektmodell für Steuerelemente oder Komponenten definiert werden oder kann es sich um eine benutzerdefinierte (d. h. von Ihnen selbst erstellte).  
  
## <a name="compile-time-and-run-time-constants"></a>Während der Kompilierung und Laufzeit-Konstanten  
 Eine Kompilierzeitkonstante wird zur Zeit berechnet, die der Code kompiliert wird, obwohl nur eine Konstante zur Laufzeit berechnet werden kann, während die Anwendung ausgeführt wird. Eine Kompilierzeitkonstante haben den gleichen Wert jedes Mal, eine Anwendung ausgeführt wird, während eine Laufzeitkonstanten jedes Mal ändern kann. Während der Kompilierung Konstanten sind z. B. Arraygrenzen, Case-Ausdrücke oder Enumerator Initialisierer erforderlich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Definition|Begriff|  
|---|---|  
|[Gewusst wie: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Erläutert, wie die `Const` -Anweisung zum Deklarieren einer Konstante und legen Sie seinen Wert; durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen, dem Wert.|  
|[Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Beschreibt wie Sie Ihre eigenen Konstanten, einschließlich Informationen zum Gültigkeitsbereich zu erstellen und um Zirkelverweise zu vermeiden.|  
|[Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Enthält Informationen darüber, wie der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler Konstanten initialisiert, wenn `Option Explicit` deaktiviert wurde.|  
|[Gewusst wie: Gruppieren verwandter konstanter Werte](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Veranschaulicht, wie Konstante Werte gruppiert, die verknüpft sind.|  
  
## <a name="reference"></a>Verweis  
  
|Definition|Begriff|  
|---|---|  
|[Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Listet die vordefinierten Konstanten [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)|Beschreibt die `Const` Anweisung und deren Verwendung.|  
|[Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Beschreibt die `Option Strict` Anweisung und deren Verwendung.|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
