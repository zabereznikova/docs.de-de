---
title: "Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Binden, mehrfach"
  - "Steuerelemente [Windows Forms], Synchronisieren mit Datenquelle"
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben
Beim Arbeiten mit Datenbindungen in Windows Forms werden häufig mehrere Steuerelemente an die gleiche Datenquelle gebunden.  In manchen Fällen müssen Sie unter Umständen anhand zusätzlicher Schritte sicherstellen, dass die gebundenen Eigenschaften der Steuerelemente untereinander und mit der Datenquelle synchronisiert bleiben.  Diese Schritte sind in zwei Situationen notwendig:  
  
-   Wenn die Datenquelle <xref:System.ComponentModel.IBindingList> nicht implementiert, und deshalb <xref:System.ComponentModel.IBindingList.ListChanged>\-Ereignisse des Typs <xref:System.ComponentModel.ListChangedType> generiert werden.  
  
-   Wenn die Datenquelle <xref:System.ComponentModel.IEditableObject> implementiert.  
  
 Im ersten Fall können Sie eine <xref:System.Windows.Forms.BindingSource>\-Komponente verwenden, um die Datenquelle an die Steuerelemente zu binden.  In letzterem Fall verwenden Sie eine <xref:System.Windows.Forms.BindingSource>\-Komponente, behandeln das <xref:System.Windows.Forms.BindingSource.BindingComplete>\-Ereignis und rufen <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> auf der zugeordneten <xref:System.Windows.Forms.BindingManagerBase> auf.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie drei Steuerelemente \(zwei Textfeldsteuerelemente und ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement\) mithilfe einer <xref:System.Windows.Forms.BindingSource>\-Komponente an die gleiche Spalte in einem <xref:System.Data.DataSet> binden können.  In diesem Beispiel wird beschrieben, wie Sie das <xref:System.Windows.Forms.BindingSource.BindingComplete>\-Ereignis behandeln müssen und wie Sie sicherstellen können, dass bei Änderungen am Textwert eines Textfelds das zusätzliche Textfeld und das <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem richtigen Wert aktualisiert werden.  
  
 Im Beispiel wird eine <xref:System.Windows.Forms.BindingSource>\-Komponente verwendet, um die Datenquelle und die Steuerelemente zu binden.  Optional können Sie die Steuerelemente direkt an die Datenquelle binden und die <xref:System.Windows.Forms.BindingManagerBase> für die Bindung aus der <xref:System.Windows.Forms.Control.BindingContext%2A>\-Eigenschaft des Formulars abrufen und dann das <xref:System.Windows.Forms.BindingManagerBase.BindingComplete>\-Ereignis für die <xref:System.Windows.Forms.BindingManagerBase> behandeln.  Auf der Hilfeseite über das <xref:System.Windows.Forms.BindingManagerBase.BindingComplete>\-Ereignis von <xref:System.Windows.Forms.BindingManagerBase> finden Sie ein Beispiel zu dieser Vorgehensweise.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
  
-   Für dieses Codebeispiel wird Folgendes benötigt:  
  
-   Verweise auf die Assemblys <xref:System>, <xref:System.Windows.Forms> und <xref:System.Drawing>  
  
-   Ein Formular mit dem behandelten <xref:System.Windows.Forms.Form.Load>\-Ereignis und ein Aufruf der `InitializeControlsAndDataSource`\-Methode im Beispiel für den <xref:System.Windows.Forms.Form.Load>\-Ereignishandler des Formulars.  
  
## Siehe auch  
 [Gewusst wie: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource\-Komponente](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)   
 [Änderungsbenachrichtigung in der Windows Forms\-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Auf Datenbindung bezogene Schnittstellen](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)