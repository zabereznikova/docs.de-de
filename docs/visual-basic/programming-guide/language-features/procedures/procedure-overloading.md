---
title: "Procedure Overloading (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "signatures"
  - "Overloads keyword"
  - "hiding by signature"
  - "Visual Basic code, procedures"
  - "procedures, signatures for"
  - "procedures, overloading"
  - "procedures, multiple versions"
  - "parameters, lists"
  - "signatures, procedure"
  - "parameter lists"
  - "Visual Basic code, parameter lists"
  - "Shadows keyword"
  - "procedure overloading"
  - "procedures, parameter lists"
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Procedure Overloading (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Unter dem *Überladen* einer Prozedur versteht man die Definition mehrerer Prozedurversionen gleichen Namens mit unterschiedlichen Parameterlisten.  Durch die Überladung können mehrere ähnliche Prozedurversionen definiert werden, ohne dass diese nach Namen voneinander unterschieden werden müssen.  Die Unterscheidung wird durch Abwandeln der Parameterlisten vorgenommen.  
  
## Überladen von Regeln  
 Für das Überladen von Prozeduren gelten folgende Regeln:  
  
-   **Gleicher Name**.  Alle überladenen Versionen müssen den gleichen Prozedurnamen verwenden.  
  
-   **Unterschiedliche Signaturen** Die überladenen Versionen müssen sich in mindestens einem der folgenden Aspekte unterscheiden:  
  
    -   Anzahl der Parameter  
  
    -   Reihenfolge der Parameter  
  
    -   Datentyp der Parameter  
  
    -   Anzahl der Typparameter \(bei einer generischen Prozedur\)  
  
    -   Rückgabetyp \(nur für einen Konvertierungsoperator\)  
  
     Zusammen mit dem Prozedurnamen werden die voranstehenden Elemente als *Signatur* der Prozedur bezeichnet.  Beim Aufruf einer überladenen Prozedur prüft der Compiler anhand der Signatur, ob der Aufruf der Definition entspricht.  
  
-   **Elemente, die nicht Teil der Signatur sind**.  Eine Prozedur kann ohne Abwandlung der Signatur nicht überladen werden.  Zum Überladen einer Prozedur ist es jedoch nicht ausreichend, nur eines oder mehrere der folgenden Elemente abzuwandeln:  
  
    -   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared` und `Static`  
  
    -   Parameter oder Typparameternamen  
  
    -   Typparametereinschränkungen \(für eine generische Prozedur\)  
  
    -   Schlüsselwörter für Parametermodifizierer, z. B. `ByRef` und `Optional`  
  
    -   Ob sie einen Wert zurückgibt  
  
    -   Datentyp des Rückgabewerts \(außer bei einem Konvertierungsoperator\)  
  
     Die Elemente in der obigen Liste sind nicht Bestandteil der Signatur.  Obwohl sie nicht zur Unterscheidung überladener Versionen verwendet werden können, können Sie sie in überladenen Versionen abwandeln, die durch ihre Signaturen ordnungsgemäß unterschieden werden.  
  
-   **Spät gebundene Argumente**.  Wenn Sie beabsichtigen, eine spät gebundene Objektvariable an eine überladene Version zu übergeben, müssen Sie den entsprechenden Parameter als <xref:System.Object> deklarieren.  
  
## Mehrere Versionen einer Prozedur  
 Angenommen, Sie schreiben eine `Sub`\-Prozedur zum Ausführen einer Transaktion mit Auswirkung auf das Kundenguthaben und möchten sich sowohl über den Namen als auch über die Kontonummer auf den Kunden beziehen können.  Dies können Sie durch die Definition zweier unterschiedlicher `Sub`\-Prozeduren erreichen, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#73](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_1.vb)]  
  
### Überladene Versionen  
 Eine Alternative stellt das Überladen eines einzelnen Prozedurnamens dar.  Um für jede Parameterliste eine Version der Prozedur zu definieren, wird das [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)\-Schlüsselwort folgendermaßen verwendet:  
  
 [!code-vb[VbVbcnProcedures#72](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_2.vb)]  
  
#### Zusätzliche Überladungen  
 Wenn auch ein Transaktionswert in `Decimal` oder `Single` akzeptiert werden soll, können Sie darüber hinaus noch `post` überladen.  Wenn Sie dies in jeder Überladung im obigen Beispiel durchgeführt hätten, hätte dies vier `Sub`\-Prozeduren gleichen Namens mit vier unterschiedlichen Signaturen ergeben.  
  
## Vorteile des Überladens  
 Der Vorteil der Prozedurüberladung liegt in der Flexibilität des Aufrufs.  Um die im letzten Beispiel deklarierte `post`\-Prozedur zu verwenden, kann der Aufrufcode die Kundenkennung entweder als `String` oder als `Integer` abrufen; in beiden Fällen wird anschließend dieselbe Prozedur aufgerufen.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbcnProcedures#56](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_4.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)