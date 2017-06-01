---
title: "Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaften&#228;nderungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Änderungsbenachrichtigungen"
  - "Datenbindung, Benachrichtigungen für Eigenschaftenänderung"
  - "Änderungsbenachrichtigungen"
  - "Eigenschaften, Änderungsbenachrichtigungen"
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaften&#228;nderungen
Um die <xref:System.Windows.Data.BindingMode>\-Bindung oder die <xref:System.Windows.Data.BindingMode>\-Bindung zu unterstützen, um die [Bindungsziel](GTMT)\-Eigenschaften zu aktivieren, um automatisch die dynamischen Änderungen der [Bindungsquelle](GTMT) widerzuspiegeln \(z. B. zur automatischen Aktualisierung des Vorschaubereichs, wenn der Benutzer ein Formular bearbeitet\), muss die Klasse die passenden Benachrichtigungen bei Eigenschaftenänderungen bereitstellen.  In diesem Beispiel wird die Erstellung einer Klasse veranschaulicht, die <xref:System.ComponentModel.INotifyPropertyChanged> implementiert.  
  
## Beispiel  
 Um <xref:System.ComponentModel.INotifyPropertyChanged> zu implementieren, müssen Sie das <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>\-Ereignis deklarieren und die `OnPropertyChanged`\-Methode erstellen.  Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Ein Beispiel für die Verwendung der `Person`\-Klasse zur Unterstützung der <xref:System.Windows.Data.BindingMode>\-Bindung finden Sie unter [Steuern, wann der TextBox\-Text die Quelle aktualisiert](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## Siehe auch  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)