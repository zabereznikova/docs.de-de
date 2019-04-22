---
title: My.Forms-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 4998097b910a504461a34af3cc159ddb1c74cc62
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832553"
---
# <a name="myforms-object"></a>My.Forms-Objekt
Stellt Eigenschaften bereit, für den Zugriff auf eine Instanz von jedem Windows-Formular, das im aktuellen Projekt deklariert.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Forms` Objekt stellt eine Instanz jedes Formular im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift.   
  
 Sie können die bereitgestellten Formulare zugreifen der `My.Forms` Objekt mit dem Namen des Formulars ohne Qualifizierung. Da die Namen der Eigenschaft den Namen des Formulars Typ identisch ist, können Sie auf ein Formular zugreifen, als hätte sie eine Standardinstanz. `My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.  
  
 Die `My.Forms` Objekt verfügbar macht, nur die Formulare, die mit dem aktuellen Projekt verknüpft ist. Er bietet Zugriff auf Formulare, die in referenzierten DLLs deklariert. Sie müssen ein Formular für den Zugriff auf, der eine DLL-Datei enthält den qualifizierten Namen des Formulars, geschrieben als verwenden *DllName*. *Formularname*.  
  
 Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> Eigenschaft zum Abrufen einer Auflistung der offenen Formulare aller Anwendungen.  
  
 Das Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.  
  
## <a name="properties"></a>Eigenschaften  
 Jede Eigenschaft der `My.Forms` -Objekt bietet Zugriff auf eine Instanz eines Formulars im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Formulars.  
  
> [!NOTE]
>  Bei ein Namenskonflikt wird der Eigenschaftsname Zugriff auf ein Formular ist *RootNamespace*_*Namespace*\_*Formularname*. Betrachten Sie z. B. zwei Formulare mit dem Namen `Form1.`eines dieser Formulare im RootNamespace ist `WindowsApplication1` und im Namespace `Namespace1`, greifen Sie auf diesem Formular kann über `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 Die `My.Forms` -Objekt bietet Zugriff auf die Instanz des Hauptformulars der Anwendung, die beim Start erstellt wurde. Für alle anderen Formen der `My.Forms` -Objekt erstellt eine neue Instanz des Formulars auf, wenn darauf zugegriffen wird, und diese speichert. Nachfolgende Versuche, diese Eigenschaft den Zugriff auf zurück diese Instanz des Formulars  
  
 Sie können durch Zuweisen eines Formulars dispose `Nothing` der Eigenschaft für dieses Formular. Der Eigenschaftensetter Ruft die <xref:System.Windows.Forms.Form.Close%2A> -Methode der das Formular, und klicken Sie dann weist `Nothing` gespeicherten Wert. Wenn Sie einen beliebigen Wert außer zuweisen `Nothing` löst der Setter der Eigenschaft ein <xref:System.ArgumentException> Ausnahme.  
  
 Sie können testen, ob eine Eigenschaft der `My.Forms` Objekt wird eine Instanz des Formulars mithilfe der `Is` oder `IsNot` Operator. Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der Eigenschaft ist `Nothing`.  
  
> [!NOTE]
>  In der Regel die `Is` oder `IsNot` Operator muss den Wert der Eigenschaft zum Ausführen des Vergleichs zu lesen. Aber wenn die Eigenschaft derzeit speichert `Nothing`, die Eigenschaft erstellt eine neue Instanz des Formulars und dann diese Instanz zurückgibt. Visual Basic-Compiler behandelt jedoch die Eigenschaften der `My.Forms` -Objekts auf andere Weise und ermöglicht die `Is` oder `IsNot` Operator, um den Status der Eigenschaft zu überprüfen, ohne Änderung ihres Werts.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Titel der standardmäßigen `SidebarMenu` Formular.  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 Für dieses Beispiel funktioniert, müssen Ihr Projekt ein Formular mit dem Namen `SidebarMenu`.  
  
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
