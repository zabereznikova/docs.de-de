---
title: "How to: Determine What Type an Object Variable Refers To (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TypeOf operator [Visual Basic], determining object variable type"
  - "variables [Visual Basic], object"
  - "object variables, determining type"
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Determine What Type an Object Variable Refers To (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Objektvariable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert sind.  Der Typ dieser Daten kann sich während der Laufzeit ändern.  Sie können jederzeit die <xref:System.Type.GetTypeCode%2A>\-Methode verwenden, um den aktuellen Laufzeittyp zu ermitteln, oder den [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md), um festzustellen, ob der aktuelle Laufzeittyp mit einem angegebenen Typ kompatibel ist.  
  
### So bestimmen Sie den Typ, auf den eine Objektvariable derzeit verweist  
  
1.  Rufen Sie für die Objektvariable die <xref:System.Object.GetType%2A>\-Methode auf, um ein <xref:System.Type?displayProperty=fullName>\-Objekt abzurufen.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  Rufen Sie für die <xref:System.Type?displayProperty=fullName>\-Klasse die freigegebene <xref:System.Type.GetTypeCode%2A>\-Methode auf, um den <xref:System.TypeCode>\-Enumerationswert für den Typ des Objekts abzurufen.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Sie können den <xref:System.TypeCode>\-Enumerationswert für alle relevanten Enumerationsmember testen, beispielsweise den Wert `Double`.  
  
### So stellen Sie fest, ob der Typ einer Objektvariablen mit einem angegebenen Typ kompatibel ist  
  
-   Verwenden Sie den Operator `TypeOf` zusammen mit dem [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md), um das Objekt mit einem `TypeOf`...`Is`\-Ausdruck zu testen.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     Der `TypeOf`...`Is`\-Ausdruck gibt `True` zurück, wenn der Laufzeittyp des Objekts mit dem angegebenen Typ kompatibel ist.  
  
     Entscheidend für die Kompatibilität ist, ob es sich bei dem angegebenen Typ um eine Klasse, Struktur oder Schnittstelle handelt.  Die Typen sind im Allgemeinen kompatibel, wenn das Objekt zum gleichen Typ gehört wie der angegebene Typ, wenn es von dem angegebenen Typ erbt oder den angegebenen Typ implementiert.  Weitere Informationen finden Sie unter [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## Kompilieren des Codes  
 Bei dem angegebenen Typ kann es sich nicht um eine Variable oder einen Ausdruck handeln.  Es muss sich um den Namen eines definierten Typs handeln, z. B. um eine Klasse, Struktur oder Schnittstelle.  Hierzu gehören systeminterne Typen wie `Integer` und `String`.  
  
## Siehe auch  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.GetTypeCode%2A>   
 <xref:System.TypeCode>   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)