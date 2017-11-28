---
title: 'Gewusst wie: Zugreifen auf Member eines Objekts (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 85fa4932b449bf7b9ecb3902fc17fd954ea8cfac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Gewusst wie: Zugreifen auf Member eines Objekts (Visual Basic)
Wenn Sie eine Objektvariable, die auf ein Objekt verweist verfügen, Sie häufig mit den Elementen des Objekts, z. B. die Methoden, Eigenschaften, Felder und Ereignisse arbeiten möchten. Angenommen, nachdem Sie erstellt haben ein neues <xref:System.Windows.Forms.Form> -Objekts können Sie möglicherweise festlegen möchten ihre <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft oder der Aufruf seiner <xref:System.Windows.Forms.Control.Focus%2A> Methode.  
  
## <a name="accessing-members"></a>Zugreifen auf Member  
 Der Member eines Objekts greifen Sie über die Variable, die darauf verweist.  
  
#### <a name="to-access-members-of-an-object"></a>Auf Member eines Objekts zuzugreifen.  
  
-   Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Objekt-Variablennamen und den Elementnamen.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Wenn das Element [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), eine Variable für den Zugriff darauf ist nicht erforderlich.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Zugreifen auf Member eines Objekts des bekannten Typs  
 Wenn Sie den Typ eines Objekts zur Kompilierungszeit kennen, können Sie *frühe Bindung* für eine Variable, die darauf verweist.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Auf Member eines Objekts, für die den Typ zur Kompilierungszeit kennen  
  
1.  Deklarieren Sie die Objektvariable vom Typ des Objekts sein, die Sie zuweisen möchten.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Mit `Option Strict On`, Sie können nur zuweisen <xref:System.Windows.Forms.Form> Objekte (oder abgeleitete Objekte eines bestimmten Typs <xref:System.Windows.Forms.Form>) zu `extraForm`. Wenn Sie eine Klasse oder Struktur mit einer erweiternden definiert haben `CType` Konvertierung in <xref:System.Windows.Forms.Form>, können Sie auch zuweisen dieser Klasse bzw. Struktur zu `extraForm`.  
  
2.  Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Objekt-Variablennamen und den Elementnamen.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Sie können Zugriff auf alle Methoden und Eigenschaften, die spezifisch für die <xref:System.Windows.Forms.Form> -Klasse, unabhängig davon, was die `Option Strict` Einstellung ist.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Zugreifen auf Member eines Objekts eines unbekannten Typs  
 Wenn Sie den Typ eines Objekts zur Kompilierzeit nicht kennen, können Sie mit *späte Bindung* für jede Variable, die darauf verweist.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Auf Member eines Objekts, für die Sie nicht den Typ zum Zeitpunkt der Kompilierung kennen  
  
1.  Deklarieren Sie die Objektvariable werden von der [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Deklarieren einer Variablen als `Object` ist identisch mit der Deklaration als <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Mit `Option Strict On`, erreichen Sie nur die Elemente, die auf definiert die <xref:System.Object> Klasse.  
  
2.  Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Objekt-Variablennamen und den Elementnamen.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Um auf die Elemente eines beliebigen Objekts zugreifen, Sie die Objektvariable zuweisen, müssen Sie festlegen `Option Strict Off`. Wenn Sie dies tun, kann der Compiler nicht garantieren, dass ein bestimmtes Element durch das Objekt verfügbar gemacht wird, die Sie der Variable zuordnen. Wenn das Objekt keinen Member verfügbar macht, Sie versuchen, den Zugriff auf, eine <xref:System.MemberAccessException> Ausnahme trat auf.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Object>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.MemberAccessException>  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
