---
title: 'Vorgehensweise: Zugreifen auf Member eines Objekts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 46c5eb9bc79b3a408a5a4fc9f40fee7391937c58
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663597"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Vorgehensweise: Zugreifen auf Member eines Objekts (Visual Basic)
Wenn Sie eine Objektvariablen, die auf ein Objekt verweist verfügen, möchten Sie häufig die Member des Objekts, z. B. die Methoden, Eigenschaften, Felder und Ereignisse zusammenarbeiten. Angenommen, nachdem Sie erstellt haben ein neues <xref:System.Windows.Forms.Form> -Objekts können Sie festlegen möchten die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft oder der Aufruf der <xref:System.Windows.Forms.Control.Focus%2A> Methode.  
  
## <a name="accessing-members"></a>Zugreifen auf Member  
 Sie können die Mitglieder eines Objekts zugreifen, über die Variable, die darauf verweist.  
  
#### <a name="to-access-members-of-an-object"></a>Auf Member eines Objekts zugreifen.  
  
- Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Namen der Objektvariablen und den Namen des Members.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Wenn der Member ist [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), eine Variable für den Zugriff ist nicht erforderlich.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Zugreifen auf Member eines Objekts vom bekannten Typ  
 Wenn Sie den Typ eines Objekts zur Kompilierungszeit kennen, können Sie *frühe Bindung* für eine Variable, die darauf verweist.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Auf Member eines Objekts, für die der Typ zur Kompilierzeit unbekannt  
  
1. Deklarieren Sie die Objektvariable vom Typ des Objekts sein, die Sie der Variable zuweisen möchten.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Mit `Option Strict On`, Sie können nur zuweisen <xref:System.Windows.Forms.Form> Objekte (oder davon abgeleitete Objekte eines Typs <xref:System.Windows.Forms.Form>) zu `extraForm`. Wenn Sie eine Klasse oder Struktur mit einer erweiternden definiert haben `CType` Konvertierung in <xref:System.Windows.Forms.Form>, Sie können auch weisen Sie dieser Klasse oder-Struktur in `extraForm`.  
  
2. Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Namen der Objektvariablen und den Namen des Members.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Sie können Zugriff auf alle Methoden und Eigenschaften, die spezifisch für die <xref:System.Windows.Forms.Form> -Klasse, unabhängig davon, was die `Option Strict` Einstellung ist.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Zugreifen auf Member eines Objekts eines unbekannten Typs  
 Wenn Sie den Typ eines Objekts zur Kompilierzeit nicht kennen, können Sie mit *späte Bindung* für jede Variable, die darauf verweist.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Auf Member eines Objekts, für die Sie nicht den Typ zur Kompilierzeit kennen  
  
1. Deklarieren Sie die Objektvariable, der die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Deklaration einer Variablen als `Object` ist identisch mit der Deklaration als <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Mit `Option Strict On`, es stehen nur die Elemente, die auf definierten die <xref:System.Object> Klasse.  
  
2. Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Namen der Objektvariablen und den Namen des Members.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Um den Zugriff auf Member eines Objekts Sie die Objektvariable zuweisen, müssen Sie festlegen, `Option Strict Off`. Wenn Sie dies tun, kann nicht der Compiler nicht garantieren, dass ein bestimmtes Element durch das Objekt verfügbar gemacht wird, die Sie der Variablen zuweisen. Wenn das Objekt keinen Member verfügbar macht, Sie versuchen, die für den Zugriff auf, eine <xref:System.MemberAccessException> Ausnahme auftritt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
