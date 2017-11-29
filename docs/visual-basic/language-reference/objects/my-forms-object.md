---
title: My.Forms-Objekt
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a>My.Forms-Objekt
Stellt Eigenschaften für den Zugriff auf eine Instanz jedes Windows Form, die im aktuellen Projekt deklariert.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Forms` Objekt enthält eine Instanz von jeder Form im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift. Informationen zum Hinzufügen von Formen zu einem Projekt finden Sie unter [wie: Hinzufügen von Windows Forms zu einem Projekt](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Sie können die bereitgestellten Formulare zugreifen, die `My.Forms` Objekt mit dem Namen des Formulars, ohne Qualifizierung. Da der Eigenschaftsname des Formulars Typnamen identisch ist, können Sie diese auf einem Formular zugreifen, als ob es sich um eine Standardinstanz hatte. `My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.  
  
 Die `My.Forms` Objekt macht nur die Formulare, die das aktuelle Projekt zugeordnet. Es bietet keine auf Formulare im referenzierten DLLs deklariert. Um ein Formular zuzugreifen, der eine DLL-Datei bereitstellt, müssen Sie den qualifizierten Namen des Formulars, geschrieben, wie Sie verwenden *DLL-Namen*. *Formularname*.  
  
 Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> Eigenschaft, um eine Auflistung von offenen Formulare der Anwendung ab.  
  
 Das Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.  
  
## <a name="properties"></a>Eigenschaften  
 Jede Eigenschaft der `My.Forms` -Objekt bietet Zugriff auf eine Instanz eines Formulars im aktuellen Projekt. Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift, und der Eigenschaftentyp entspricht der Typ des Formulars.  
  
> [!NOTE]
>  Ist ein Konflikt von geschachteltem Klassennamen, der Name der Zugriff auf ein Formular ist *RootNamespace*_*Namespace*\_*Formularname*. Betrachten Sie z. B. zwei Formulare mit dem Namen `Form1.`Wenn eines dieser Formulare im Stammnamespace ist `WindowsApplication1` und im Namespace `Namespace1`, würden Sie dieses Formular über zugreifen `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 Die `My.Forms` -Objekt bietet Zugriff auf die Instanz von Hauptformular der Anwendung, die beim Start erstellt wurde. Für jede andere Form der `My.Forms` Objekt erstellt eine neue Instanz des Formulars aus, wenn er Zugriff auf und sie speichert. Nachfolgende Versuche, die Zugriff auf diese Eigenschaft zurückgeben dieser Instanz des Formulars.  
  
 Sie können durch Zuweisen eines Formulars dispose `Nothing` für die Eigenschaft für das Formular. Der Eigenschaftensetter Ruft die <xref:System.Windows.Forms.Form.Close%2A> -Methode des Formulars, und klicken Sie dann weist `Nothing` mit dem gespeicherten Wert. Wenn Sie einen beliebigen Wert außer zuweisen `Nothing` der Eigenschaft Setter-Methode löst eine <xref:System.ArgumentException> Ausnahme.  
  
 Sie können testen, ob eine Eigenschaft der `My.Forms` Objekt speichert eine Instanz des Formulars mit der `Is` oder `IsNot` Operator. Sie können diese Operatoren verwenden, zum Überprüfen, ob der Wert der Eigenschaft ist `Nothing`.  
  
> [!NOTE]
>  In der Regel die `Is` oder `IsNot` Operator muss den Wert der Eigenschaft zum Ausführen des Vergleichs zu lesen. Jedoch, wenn die Eigenschaft aktuell speichert `Nothing`, die Eigenschaft erstellt eine neue Instanz des Formulars und gibt dann diese Instanz zurück. Visual Basic-Compiler behandelt jedoch die Eigenschaften der `My.Forms` Objekt unterschiedlich, und ermöglicht die `Is` oder `IsNot` Operator, um den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Titel des Standardwerts `SidebarMenu` Formular.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Für dieses Beispiel funktioniert, muss das Projekt ein Formular mit dem Namen verfügen `SidebarMenu`. Weitere Informationen finden Sie unter [wie: Hinzufügen von Windows Forms zu einem Projekt](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
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
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [Objekte](../../../visual-basic/language-reference/objects/index.md)  
 [Vorgehensweise: Hinzufügen von Windows Forms zu einem Projekt](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Zugreifen auf Anwendungsformulare](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
