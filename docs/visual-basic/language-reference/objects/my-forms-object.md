---
title: My.Forms-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 001f6fbfae2467ea0af5e98ca041b694d1e7b8f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372439"
---
# <a name="myforms-object"></a>My.Forms-Objekt

Stellt Eigenschaften für den Zugriff auf eine Instanz der einzelnen im aktuellen Projekt deklarierten Windows Forms bereit.

## <a name="remarks"></a>Bemerkungen

Das- `My.Forms` Objekt stellt eine Instanz der einzelnen Formulare im aktuellen Projekt bereit. Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift.

Sie können auf die Formulare zugreifen, die vom-Objekt bereitgestellt werden `My.Forms` , indem Sie den Namen des Formulars ohne Qualifikation verwenden. Da der Eigenschaftsname mit dem Typnamen des Formulars identisch ist, können Sie auf ein Formular zugreifen, als wäre es eine Standard Instanz. `My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.

Das- `My.Forms` Objekt macht nur die dem aktuellen Projekt zugeordneten Formulare verfügbar. Der Zugriff auf Formulare, die in referenzierten DLLs deklariert sind, ist nicht möglich. Wenn Sie auf ein Formular zugreifen möchten, das eine DLL bereitstellt, müssen Sie den qualifizierten Namen des Formulars verwenden, der als *dllName*geschrieben wurde. *FormName*.

Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> -Eigenschaft verwenden, um eine Auflistung aller geöffneten Formulare der Anwendung zu erhalten.

Das-Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.

## <a name="properties"></a>Eigenschaften

Jede Eigenschaft des- `My.Forms` Objekts ermöglicht den Zugriff auf eine Instanz eines Formulars im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Formulars.

> [!NOTE]
> Wenn ein namens Konflikt vorliegt, ist der Eigenschaftsname für den Zugriff auf ein Formular *RootNamespace*_*Namespace* \_ *FormName*. Sehen Sie sich beispielsweise zwei Formulare mit `Form1.` dem Namen an, wenn sich eines dieser Formulare im Stamm Namespace `WindowsApplication1` und im-Namespace befindet `Namespace1` , auf dieses Formular überzugreifen `My.Forms.WindowsApplication1_Namespace1_Form1` .

Das `My.Forms` -Objekt ermöglicht den Zugriff auf die Instanz des Haupt Formulars der Anwendung, das beim Start erstellt wurde. Bei allen anderen Formularen erstellt das- `My.Forms` Objekt eine neue Instanz des Formulars, wenn darauf zugegriffen wird, und speichert es. Bei nachfolgenden versuchen, auf diese Eigenschaft zuzugreifen, wird diese Instanz des Formulars zurückgegeben.

Sie können ein Formular verwerfen, indem Sie `Nothing` die-Eigenschaft für dieses Formular zuweisen. Der Eigenschaften Setter Ruft die <xref:System.Windows.Forms.Form.Close%2A> -Methode des Formulars auf und weist dann `Nothing` dem gespeicherten Wert zu. Wenn Sie der-Eigenschaft einen anderen Wert als zuweisen `Nothing` , löst der Setter eine <xref:System.ArgumentException> Ausnahme aus.

Sie können mithilfe des OR-Operators testen, ob eine Eigenschaft des `My.Forms` Objekts eine Instanz des Formulars `Is` speichert `IsNot` . Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der-Eigenschaft ist `Nothing` .

> [!NOTE]
> In der Regel `Is` muss der-Operator oder der- `IsNot` Operator den Wert der-Eigenschaft lesen, um den Vergleich durchzuführen. Wenn die Eigenschaft derzeit jedoch gespeichert `Nothing` wird, erstellt die-Eigenschaft eine neue Instanz des Formulars und gibt diese Instanz zurück. Der Visual Basic Compiler behandelt jedoch die Eigenschaften des `My.Forms` Objekts anders und ermöglicht dem or- `Is` `IsNot` Operator, den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.

## <a name="example"></a>Beispiel

In diesem Beispiel wird der Titel des Standard `SidebarMenu` Formulars geändert.

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

Damit dieses Beispiel funktioniert, muss das Projekt über ein Formular mit dem Namen verfügen `SidebarMenu` .

Dieser Code funktioniert nur in einem Windows-Anwendungsprojekt.

## <a name="requirements"></a>Anforderungen

### <a name="availability-by-project-type"></a>Verfügbarkeit nach Projekttyp

|Projekttyp:|Verfügbar|
|---|---|
|Windows-Anwendung|**Ja**|
|Klassenbibliothek|Nein|
|Konsolenanwendung|Nein|
|Windows-Steuerelementbibliothek|Nein|
|Websteuerelementbibliothek|Nein|
|&Windows-Dienst|Nein|
|Website|Nein|

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [Objekte](index.md)
- [Is-Operator](../operators/is-operator.md)
- [IsNot-Operator](../operators/isnot-operator.md)
- [Zugreifen auf Anwendungsformulare](../../developing-apps/programming/accessing-application-forms.md)
