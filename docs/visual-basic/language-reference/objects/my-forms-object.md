---
title: My.Forms-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350374"
---
# <a name="myforms-object"></a>My.Forms-Objekt

Stellt Eigenschaften für den Zugriff auf eine Instanz der einzelnen im aktuellen Projekt deklarierten Windows Forms bereit.

## <a name="remarks"></a>Hinweise

Das `My.Forms`-Objekt stellt eine Instanz jedes Formulars im aktuellen Projekt bereit. Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift.

Sie können auf die vom `My.Forms` Objekt bereitgestellten Formulare zugreifen, indem Sie den Namen des Formulars ohne Qualifikation verwenden. Da der Eigenschaftsname mit dem Typnamen des Formulars identisch ist, können Sie auf ein Formular zugreifen, als wäre es eine Standard Instanz. `My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.

Das `My.Forms`-Objekt macht nur die dem aktuellen Projekt zugeordneten Formulare verfügbar. Der Zugriff auf Formulare, die in referenzierten DLLs deklariert sind, ist nicht möglich. Wenn Sie auf ein Formular zugreifen möchten, das eine DLL bereitstellt, müssen Sie den qualifizierten Namen des Formulars verwenden, der als *dllName*geschrieben wurde. *FormName*.

Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>-Eigenschaft verwenden, um eine Sammlung aller geöffneten Formulare der Anwendung zu erhalten.

Das-Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.

## <a name="properties"></a>Eigenschaften

Jede Eigenschaft des `My.Forms` Objekts ermöglicht den Zugriff auf eine Instanz eines Formulars im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Formulars.

> [!NOTE]
> Wenn ein namens Konflikt vorliegt, ist der Eigenschaftsname für den Zugriff auf ein Formular *RootNamespace*_*Namespace*\_*FormName*. Nehmen Sie beispielsweise zwei Formulare mit dem Namen `Form1.`, wenn sich eines dieser Formulare im Stamm Namespace befindet `WindowsApplication1` und im Namespace `Namespace1`auf dieses Formular über `My.Forms.WindowsApplication1_Namespace1_Form1`zugreifen.

Das `My.Forms`-Objekt ermöglicht den Zugriff auf die Instanz des Haupt Formulars der Anwendung, das beim Start erstellt wurde. Bei allen anderen Formularen erstellt das `My.Forms`-Objekt eine neue Instanz des Formulars, wenn darauf zugegriffen wird, und speichert es. Bei nachfolgenden versuchen, auf diese Eigenschaft zuzugreifen, wird diese Instanz des Formulars zurückgegeben.

Sie können ein Formular verwerfen, indem Sie `Nothing` der-Eigenschaft für dieses Formular zuweisen. Der Eigenschaften Setter Ruft die <xref:System.Windows.Forms.Form.Close%2A>-Methode des Formulars auf und weist dann `Nothing` dem gespeicherten Wert zu. Wenn Sie der-Eigenschaft einen anderen Wert als `Nothing` zuweisen, löst der Setter eine <xref:System.ArgumentException>-Ausnahme aus.

Sie können überprüfen, ob eine Eigenschaft des `My.Forms` Objekts eine Instanz des Formulars speichert, indem Sie den `Is`-oder `IsNot`-Operator verwenden. Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der Eigenschaft `Nothing`ist.

> [!NOTE]
> In der Regel muss der `Is` oder `IsNot` Operator den Wert der-Eigenschaft lesen, um den Vergleich durchzuführen. Wenn die Eigenschaft derzeit jedoch `Nothing`speichert, erstellt die-Eigenschaft eine neue Instanz des Formulars und gibt diese Instanz zurück. Der Visual Basic Compiler behandelt jedoch die Eigenschaften des `My.Forms` Objekts anders und ermöglicht es dem `Is` oder `IsNot` Operator, den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.

## <a name="example"></a>Beispiel

In diesem Beispiel wird der Titel des Standard `SidebarMenu` Formulars geändert.

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

Damit dieses Beispiel funktioniert, muss das Projekt über ein Formular mit dem Namen `SidebarMenu`verfügen.

Dieser Code funktioniert nur in einem Windows-Anwendungsprojekt.

## <a name="requirements"></a>Voraussetzungen

### <a name="availability-by-project-type"></a>Verfügbarkeit nach Projekttyp

|Projekttyp:|Verfügbar|
|---|---|
|Windows-Anwendung|**Ja**|
|Klassenbibliothek|Nein|
|Konsolenanwendung|Nein|
|Windows-Steuerelement Bibliothek|Nein|
|Websteuer Element Bibliothek|Nein|
|Windows-Dienst|Nein|
|Website|Nein|

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [Objekte](../../../visual-basic/language-reference/objects/index.md)
- [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Zugreifen auf Anwendungsformulare](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
