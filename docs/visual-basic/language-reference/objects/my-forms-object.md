---
title: My. Forms-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9fa5c77dd12c98100e3d17fc473a6802180d1e32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965984"
---
# <a name="myforms-object"></a>My.Forms-Objekt
Stellt Eigenschaften für den Zugriff auf eine Instanz der einzelnen im aktuellen Projekt deklarierten Windows Forms bereit.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Forms` -Objekt stellt eine Instanz der einzelnen Formulare im aktuellen Projekt bereit. Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift.   
  
 Sie können auf die Formulare zugreifen, die `My.Forms` vom-Objekt bereitgestellt werden, indem Sie den Namen des Formulars ohne Qualifikation verwenden. Da der Eigenschaftsname mit dem Typnamen des Formulars identisch ist, können Sie auf ein Formular zugreifen, als wäre es eine Standard Instanz. `My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.  
  
 Das `My.Forms` -Objekt macht nur die dem aktuellen Projekt zugeordneten Formulare verfügbar. Der Zugriff auf Formulare, die in referenzierten DLLs deklariert sind, ist nicht möglich. Wenn Sie auf ein Formular zugreifen möchten, das eine DLL bereitstellt, müssen Sie den qualifizierten Namen des Formulars verwenden, der als *dllName*geschrieben wurde. *FormName*.  
  
 Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> -Eigenschaft verwenden, um eine Auflistung aller geöffneten Formulare der Anwendung zu erhalten.  
  
 Das-Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.  
  
## <a name="properties"></a>Eigenschaften  
 Jede Eigenschaft des `My.Forms` -Objekts ermöglicht den Zugriff auf eine Instanz eines Formulars im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Formulars.  
  
> [!NOTE]
> Wenn ein namens Konflikt vorliegt, ist der Eigenschaftsname für den Zugriff auf ein Formular *RootNamespace*_*Namespace*\_*FormName*. Sehen Sie sich beispielsweise zwei Formulare `Form1.`mit dem Namen an, wenn sich eines dieser Formulare im `WindowsApplication1` Stamm Namespace und im `Namespace1`-Namespace befindet, auf dieses `My.Forms.WindowsApplication1_Namespace1_Form1`Formular überzugreifen.  
  
 Das `My.Forms` -Objekt ermöglicht den Zugriff auf die Instanz des Haupt Formulars der Anwendung, das beim Start erstellt wurde. Bei allen anderen Formularen erstellt das `My.Forms` -Objekt eine neue Instanz des Formulars, wenn darauf zugegriffen wird, und speichert es. Bei nachfolgenden versuchen, auf diese Eigenschaft zuzugreifen, wird diese Instanz des Formulars zurückgegeben.  
  
 Sie können ein Formular verwerfen, indem Sie `Nothing` die-Eigenschaft für dieses Formular zuweisen. Der Eigenschaften Setter Ruft die <xref:System.Windows.Forms.Form.Close%2A> -Methode des Formulars auf und weist `Nothing` dann dem gespeicherten Wert zu. Wenn Sie der-Eigenschaft einen anderen `Nothing` Wert als zuweisen, löst der Setter eine <xref:System.ArgumentException> Ausnahme aus.  
  
 Sie können mithilfe des `My.Forms` `Is` or `IsNot` -Operators testen, ob eine Eigenschaft des Objekts eine Instanz des Formulars speichert. Sie können diese Operatoren verwenden, um zu überprüfen, ob der `Nothing`Wert der-Eigenschaft ist.  
  
> [!NOTE]
> In der Regel `Is` muss `IsNot` der-Operator oder der-Operator den Wert der-Eigenschaft lesen, um den Vergleich durchzuführen. Wenn die Eigenschaft derzeit jedoch gespeichert `Nothing`wird, erstellt die-Eigenschaft eine neue Instanz des Formulars und gibt diese Instanz zurück. Der Visual Basic Compiler behandelt jedoch die Eigenschaften des `My.Forms` Objekts anders und ermöglicht dem `Is` or `IsNot` -Operator, den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Titel des Standard `SidebarMenu` Formulars geändert.  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 Damit dieses Beispiel funktioniert, muss das Projekt über ein Formular mit dem `SidebarMenu`Namen verfügen.  
  
 Dieser Code funktioniert nur in einem Windows-Anwendungsprojekt.  
  
## <a name="requirements"></a>Anforderungen  
  
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
