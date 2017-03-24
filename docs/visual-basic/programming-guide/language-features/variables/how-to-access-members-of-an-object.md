---
title: "How to: Access Members of an Object (Visual Basic) | Microsoft Docs"
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
  - "members, accessing"
  - "object variables, accessing members"
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Access Members of an Object (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn eine Objektvariable gegeben ist, die auf ein Objekt verweist, wird häufig der Fall eintreten, dass Sie die Member dieses Objekts, z. B. seine Methoden, Eigenschaften, Felder und Ereignisse, verwenden möchten.  Wenn Sie beispielsweise ein neues <xref:System.Windows.Forms.Form>\-Objekt erstellt haben, möchten Sie wahrscheinlich dessen <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft festlegen oder seine <xref:System.Windows.Forms.Control.Focus%2A>\-Methode aufrufen.  
  
## Zugreifen auf Member  
 Auf die Member eines Objekts greifen Sie über die Variable zu, die auf das Objekt verweist.  
  
#### So greifen Sie auf Member eines Objekts zu  
  
-   Geben Sie den Memberzugriff\-Operator \(`.`\) zwischen dem Objektvariablennamen und dem Membernamen an.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Wenn der Member als [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) deklariert ist, benötigen Sie keine Variable für den Zugriff.  
  
## Zugreifen auf Member eines Objekts eines bekannten Typs  
 Wenn Sie zur Kompilierungszeit den Typ eines Objekts kennen, können Sie für eine Variable, die darauf verweist, die *frühe Bindung* verwenden.  
  
#### So greifen Sie auf Member eines Objekts zu, dessen Typ Sie zur Kompilierungszeit kennen  
  
1.  Deklarieren Sie die Objektvariable mit dem Typ des Objekts, das Sie der Variablen zuweisen möchten.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form   
    ```  
  
     Wenn `Option Strict On` angegeben ist, können Sie nur <xref:System.Windows.Forms.Form>\-Objekte \(oder Objekte eines von <xref:System.Windows.Forms.Form> abgeleiteten Typs\) `extraForm` zuweisen.  Wenn Sie eine Klasse oder Struktur mit einer erweiternden `CType` Konvertierung als <xref:System.Windows.Forms.Form> definiert haben, können Sie auch diese Klasse oder Struktur `extraForm` zuweisen.  
  
2.  Geben Sie den Memberzugriff\-Operator \(`.`\) zwischen dem Objektvariablennamen und dem Membernamen an.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Sie können unabhängig von der aktuellen `Option Strict`\-Einstellung auf alle Methoden und Eigenschaften zugreifen, die der <xref:System.Windows.Forms.Form>\-Klasse eigen sind.  
  
## Zugreifen auf Member eines Objekts eines unbekannten Typs  
 Wenn Sie zur Kompilierungszeit den Typ eines Objekts nicht kennen, müssen Sie für jede Variable, die darauf verweist, die *späte Bindung* verwenden.  
  
#### So greifen Sie auf Member eines Objekts zu, dessen Typ Sie zur Kompilierungszeit nicht kennen  
  
1.  Deklarieren Sie die Objektvariable als [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)\-Typ.  \(Wenn eine Variable als `Object` deklariert wird, ist dies gleichbedeutend mit einer Deklaration als <xref:System.Object?displayProperty=fullName>.\)  
  
    ```  
    Dim someControl As Object   
    ```  
  
     Wenn `Option Strict On` aktiviert ist, können Sie nur auf die Member zugreifen, die in der <xref:System.Object>\-Klasse definiert sind.  
  
2.  Geben Sie den Memberzugriff\-Operator \(`.`\) zwischen dem Objektvariablennamen und dem Membernamen an.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Damit Sie auf die Member jedes beliebigen Objekts, das der Objektvariablen zugewiesen wird, zugreifen können, müssen Sie `Option Strict Off` festlegen.  Wenn Sie diese Einstellung wählen, kann der Compiler nicht garantieren, dass ein gegebener Member für das Objekt verfügbar ist, das Sie der Variablen zuweisen.  Wird ein Member, auf das Sie zuzugreifen versuchen, vom Objekt nicht verfügbar gemacht, tritt eine <xref:System.MemberAccessException>\-Ausnahme auf.  
  
## Siehe auch  
 <xref:System.Object>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.MemberAccessException>   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)