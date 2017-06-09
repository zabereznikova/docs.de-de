---
title: "Gewusst wie: &#196;ndern der Rahmen von Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, Ändern der Rahmen"
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: &#196;ndern der Rahmen von Windows Forms
Sie können aus mehreren Rahmenformatvorlagen auswählen, wenn Sie das Aussehen und Verhalten Ihres Windows Forms\-Elements festlegen möchten.  Durch Ändern der <xref:System.Windows.Forms.Form.FormBorderStyle%2A>\-Eigenschaft können Sie das Verhalten des Formulars bei das Größenanpassung steuern.  Zudem wirkt sich das Festlegen von <xref:System.Windows.Forms.Form.FormBorderStyle%2A> darauf aus, wie die Titelleiste angezeigt wird und mit welchen Schaltflächen.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.FormBorderStyle>.  
  
 In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] wird diese Aufgabe umfassend unterstützt.  
  
 Siehe auch [Gewusst wie: Ändern der Rahmen von Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).  
  
### So legen Sie die Rahmenart von Windows Forms programmgesteuert fest  
  
-   Legen Sie die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf die gewünschte Rahmenart fest.  Im folgenden Codebeispiel wird die Rahmenart des Formulars `DlgBx1`  auf <xref:System.Windows.Forms.FormBorderStyle> festgelegt.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     Siehe auch [Gewusst wie: Erstellen von Dialogfeldern zur Entwurfszeit](http://msdn.microsoft.com/library/55cz5x2c%20\(v=vs.110\)).  
  
     Wenn Sie eine Rahmenart für das Formular ausgewählt haben, die optionale Schaltflächen **Minimieren** und **Maximieren** enthält, können Sie außerdem angeben, ob eine Schaltfläche oder beide Schaltflächen funktionsfähig sein sollen.  Diese Schaltflächen sind hilfreich, wenn Sie die Benutzeroberfläche genau steuern möchten.  Die Schaltflächen **Minimieren** und **Maximieren** sind standardmäßig aktiviert, und ihre Funktionalität wird über das Fenster **Eigenschaften** gesteuert.  
  
## Siehe auch  
 <xref:System.Windows.Forms.FormBorderStyle>   
 <xref:System.Windows.Forms.FormBorderStyle>   
 [Erste Schritte mit Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)