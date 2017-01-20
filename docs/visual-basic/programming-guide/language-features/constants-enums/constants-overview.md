---
title: "Constants Overview (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constants"
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Constants Overview (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine Konstante ist ein aussagekräftiger Name, der anstelle einer unveränderlichen Zahl oder Zeichenfolge verwendet wird.  Konstanten speichern Werte, die \(wie der Name sagt\) während der Ausführung einer Anwendung konstant bleiben.  Sie können durch die Verwendung von Konstanten die Lesbarkeit des Codes erheblich verbessern und die Verwaltung vereinfachen.  Benutzen Sie sie in Code, der häufig wiederkehrende Werte oder bestimmte Zahlen enthält, die man sich schwer merken kann oder die keine offensichtliche Bedeutung haben.  
  
## Gewusst wie: Erstellen und Verwenden von Konstanten  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] enthält eine Reihe vordefinierter Konstanten, die hauptsächlich zum Drucken und Anzeigen verwendet werden.  Sie können mit der `Const`\-Anweisung auch selbst Konstanten erstellen. Dabei gelten die gleichen Richtlinien wie bei der Erstellung eines Variablennamens.  Wenn `Option Strict` den Wert `On` hat, müssen Sie den Konstantentyp explizit deklarieren.  
  
 Der Gültigkeitsbereich einer Konstanten, d. h. die gesamte Codemenge, in der auf sie verwiesen werden kann, ohne dass darin ihr Name qualifiziert wird, entspricht dem einer an derselben Position deklarierten Variablen.  Wenn Sie eine Konstante erstellen möchten, die innerhalb des Gültigkeitsbereichs einer bestimmten Prozedur vorhanden sein soll, müssen Sie die Konstante innerhalb der Prozedur deklarieren.  Wenn die Konstante innerhalb der gesamten Anwendung verfügbar sein soll, deklarieren Sie sie mithilfe des `Public`\-Schlüsselworts im Deklarationsabschnitt der Klasse.  
  
> [!NOTE]
>  Obwohl Konstanten in bestimmter Hinsicht Variablen ähneln, können Sie Konstanten nicht wie Variablen ändern oder ihnen neue Werte zuordnen.  
  
 Die im Code verwendeten Konstanten können systeminterne Konstanten des verwendeten Objektmodells für Steuerelemente bzw. Komponenten oder aber benutzerdefinierte \(d. h. von Ihnen selbst erstellte\) Konstanten sein.  
  
## Kompilierungszeitkonstanten und Laufzeitkonstanten  
 Kompilierungszeitkonstanten werden während der Codekompilierung berechnet. Laufzeitkonstanten werden dagegen nur während der Ausführung der Anwendung berechnet.  Kompilierungszeitkonstanten haben bei jeder Ausführung der Anwendung den gleichen Wert, während sich der Wert von Laufzeitkonstanten jedes Mal ändern kann.  Kompilierungszeitkonstanten sind z. B. im Zusammenhang mit Arraygrenzen, case\-Ausdrücken oder Enumeratorinitialisierungen erforderlich.  
  
## In diesem Abschnitt  
  
|||  
|-|-|  
|Definition|Begriff|  
|[How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Erläutert die Verwendung der `Const`\-Anweisung zum Deklarieren einer Konstante und zum Festlegen ihres Werts. Durch die Deklaration einer Konstante weisen Sie dem Wert einen aussagekräftigen Namen zu.|  
|[User\-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Beschreibt die Erstellung eigener Konstanten mit Informationen zum Gültigkeitsbereich und zur Vermeidung zirkulärer Verweise.|  
|[Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Stellt Informationen darüber bereit, wie der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler Konstanten initialisiert, wenn `Option Explicit` deaktiviert ist.|  
|[How to: Group Related Constant Values Together](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Veranschaulicht, wie verknüpfte konstante Werte gruppiert werden.|  
  
## Verweise  
  
|||  
|-|-|  
|Definition|Begriff|  
|[Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Führt die von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] vordefinierten Konstanten auf.|  
|[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)|Beschreibt die `Const`\-Anweisung und ihre Verwendung.|  
|[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Beschreibt die `Option Strict`\-Anweisung und ihre Verwendung.|  
  
## Siehe auch  
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)