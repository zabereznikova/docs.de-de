---
title: 'Vorgehensweise: Zugreifen auf Member eines Objekts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 882046b829ade2da7c10b3db4c0d6c9ca9f3d579
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630829"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Vorgehensweise: Zugreifen auf Member eines Objekts (Visual Basic)

Wenn Sie über eine Objekt Variable verfügen, die auf ein Objekt verweist, sollten Sie häufig mit den Membern dieses Objekts arbeiten, z. b. die Methoden, Eigenschaften, Felder und Ereignisse. Wenn Sie z. b. ein neues <xref:System.Windows.Forms.Form> -Objekt erstellt haben, möchten Sie möglicherweise seine <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft festlegen <xref:System.Windows.Forms.Control.Focus%2A> oder die zugehörige-Methode aufzurufen.

## <a name="accessing-members"></a>Zugreifen auf Member

Sie greifen auf die Member eines Objekts über die Variable zu, die darauf verweist.

#### <a name="to-access-members-of-an-object"></a>So greifen Sie auf Member eines Objekts zu

- Verwenden Sie den Member-Access-`.`Operator () zwischen dem Objektvariablen Namen und dem Elementnamen.

    ```vb
    currentText = newForm.Text
    ```

    Wenn der Member frei [gegeben](../../../../visual-basic/language-reference/modifiers/shared.md)ist, benötigen Sie keine Variable, um darauf zuzugreifen.

## <a name="accessing-members-of-an-object-of-known-type"></a>Zugreifen auf Member eines Objekts des bekannten Typs

Wenn Sie den Typ eines Objekts zur Kompilierzeit kennen, können Sie eine *frühe Bindung* für eine Variable verwenden, die darauf verweist.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>So greifen Sie auf Member eines Objekts zu, für das Sie den Typ zur Kompilierzeit kennen

1. Deklarieren Sie die Objekt Variable als Typ des Objekts, das Sie der Variablen zuweisen möchten.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    Mit `Option Strict On`können Sie nur <xref:System.Windows.Forms.Form> Objekte (oder Objekte eines Typs, die von <xref:System.Windows.Forms.Form>abgeleitet sind) zu `extraForm`zuweisen. Wenn Sie eine Klasse oder Struktur mit erweiternde `CType` Konvertierung in <xref:System.Windows.Forms.Form>definiert haben, können Sie `extraForm`diese Klasse oder Struktur auch zuweisen.

2. Verwenden Sie den Member-Access-`.`Operator () zwischen dem Objektvariablen Namen und dem Elementnamen.

    ```vb
    extraForm.Show()
    ```

    Unabhängig von der `Option Strict` Einstellung können Sie auf alle Methoden und Eigenschaften zugreifen <xref:System.Windows.Forms.Form> , die für die-Klasse spezifisch sind.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Zugreifen auf Member eines Objekts mit einem unbekannten Typ

Wenn Sie den Typ eines Objekts zur Kompilierzeit nicht kennen, müssen Sie für jede Variable, die darauf verweist, die *späte Bindung* verwenden.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>So greifen Sie auf Member eines Objekts zu, für das der Typ zur Kompilierzeit nicht bekannt ist

1. Deklarieren Sie die Objekt Variable als [Objekt Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Das Deklarieren einer `Object` Variablen als entspricht der Deklaration <xref:System.Object?displayProperty=nameWithType>als.)

    ```vb
    Dim someControl As Object
    ```

    Mit `Option Strict On`können Sie nur auf die Member zugreifen, die für die <xref:System.Object> -Klasse definiert sind.

2. Verwenden Sie den Member-Access-`.`Operator () zwischen dem Objektvariablen Namen und dem Elementnamen.

    ```vb
    someControl.GetType()
    ```

    Um auf die Member eines beliebigen Objekts zugreifen zu können, das Sie der Objektvariablen zuweisen, müssen Sie `Option Strict Off`festlegen. Wenn Sie dies tun, kann der Compiler nicht garantieren, dass ein angegebenes Element von dem Objekt verfügbar gemacht wird, das Sie der Variablen zuweisen. Wenn das-Objekt keinen Member verfügbar macht, auf den Sie zugreifen möchten <xref:System.MemberAccessException> , wird eine-Ausnahme ausgelöst.

## <a name="see-also"></a>Siehe auch

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
