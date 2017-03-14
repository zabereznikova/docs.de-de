---
title: "My.Forms Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.Forms"
  - "My.MyProject.Forms"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Forms object"
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# My.Forms Object
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Stellt Eigenschaften für den Zugriff auf eine Instanz jedes im aktuellen Projekt deklarierten Windows Form bereit.  
  
## Hinweise  
 Das `My.Forms`\-Objekt stellt eine Instanz jedes Formulars im aktuellen Projekt bereit.  Der Name der Eigenschaft stimmt mit dem Namen des Formulars überein, auf das die Eigenschaft zugreift.  Informationen über das Hinzufügen von Formularen zu einem Projekt finden Sie unter [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/de-de/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Sie können mit dem Namen des Formulars ohne Qualifizierung auf die vom `My.Forms`\-Objekt bereitgestellten Formulare zugreifen.  Da der Eigenschaftenname mit dem Typnamen des Formulars übereinstimmt, können Sie auf das Formular wie auf ein Formular zugreifen, das über eine Standardinstanz verfügt.  `My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.  
  
 Das `My.Forms`\-Objekt macht nur die dem aktuellen Projekt zugeordneten Formulare verfügbar.  Es stellt keinen Zugriff auf Formulare bereit, die in DLLs deklariert sind, auf die verwiesen wird.  Um auf ein Formular zuzugreifen, das von einer DLL bereitgestellt wird, müssen Sie den qualifizierten Namen des Formulars im Format *DLL\-Name*.*Formularname* verwenden.  
  
 Mit der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>\-Eigenschaft können Sie eine Auflistung aller geöffneten Formulare der Anwendung abrufen.  
  
 Das Objekt und seine Eigenschaften sind nur für Windows\-Anwendungen verfügbar.  
  
## Eigenschaften  
 Jede Eigenschaft des `My.Forms`\-Objekts ermöglicht den Zugriff auf eine Instanz eines Formulars im aktuellen Projekt.  Der Name der Eigenschaft stimmt mit dem Namen des Formulars überein, auf den die Eigenschaft zugreift, und der Eigenschaftentyp stimmt mit dem Typ des Formulars überein.  
  
> [!NOTE]
>  Wenn ein Namenskonflikt besteht, lautet der Eigenschaftenname für den Zugriff auf ein Formular *Stammnamespace*\_*Namespace*\_*Formularname*.  Angenommen, zwei Formulare heißen `Form1.`. Wenn sich eines dieser Formulare im Stammnamespace `WindowsApplication1` und im Namespace `Namespace1` befindet, greifen Sie auf dieses Formular über `My.Forms.WindowsApplication1_Namespace1_Form1` zu.  
  
 Das `My.Forms`\-Objekt ermöglicht den Zugriff auf die Instanz des Hauptformulars der Anwendung, das beim Starten der Anwendung erstellt wurde.  Für alle anderen Formulare erstellt das `My.Forms`\-Objekt eine neue Instanz des Formulars, wenn darauf zugegriffen wird, und speichert diese.  Bei anschließenden Versuchen, auf diese Eigenschaft zuzugreifen, wird die Instanz des Formulars zurückgegeben.  
  
 Sie können ein Formular freigeben, indem Sie der Eigenschaft für das Formular `Nothing` zuweisen.  Der Eigenschaftensetter ruft die <xref:System.Windows.Forms.Form.Close%2A>\-Methode des Formulars auf und weist anschließend dem gespeicherten Wert `Nothing` zu.  Wenn Sie der Eigenschaft einen anderen Wert als `Nothing` zuweisen, löst der Setter eine <xref:System.ArgumentException>\-Ausnahme aus.  
  
 Mit dem Operator `Is` oder dem Operator `IsNot` können Sie überprüfen, ob eine Eigenschaft des `My.Forms`\-Objekts eine Instanz des Formulars speichert.  Sie können mit diesen Operatoren überprüfen, ob der Wert der Eigenschaft `Nothing` ist.  
  
> [!NOTE]
>  Normalerweise muss der Operator `Is` oder der Operator `IsNot` den Wert der Eigenschaft lesen, um den Vergleich durchzuführen..  Wenn die Eigenschaft gegenwärtig jedoch `Nothing` speichert, erstellt sie eine neue Instanz des Formulars und gibt dann diese Instanz zurück.  Der Visual Basic\-Compiler behandelt aber die Eigenschaften des `My.Forms`\-Objekts auf andere Weise und lässt das Überprüfen des Status der Eigenschaft durch den Operator `Is` oder den Operator `IsNot` ohne eine Änderung ihres Werts zu.  
  
## Beispiel  
 In diesem Beispiel wird der Titel des Standardformulars `SidebarMenu` geändert.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Damit diese Beispiel ausgeführt werden kann, muss das Projekt das Formular `SidebarMenu` enthalten.  Weitere Informationen finden Sie unter [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/de-de/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Dieser Code kann nur in einem Windows\-Anwendungsprojekt ausgeführt werden.  
  
## Anforderungen  
  
### Verfügbarkeit nach Projekttyp  
  
|||  
|-|-|  
|Projekttyp|Verfügbar|  
|Windows\-Anwendung|**Ja**|  
|Klassenbibliothek|Nein|  
|Konsolenanwendung|Nein|  
|Windows\-Steuerelementbibliothek|Nein|  
|Web\-Steuerelementbibliothek|Nein|  
|Windows\-Dienst|Nein|  
|Website|Nein|  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.Windows.Forms.Form.Close%2A>   
 [Objects](../../../visual-basic/language-reference/objects/index.md)   
 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/de-de/3d7bb25f-fd90-47cf-9378-fa0d764686c1)   
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Accessing Application Forms](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)