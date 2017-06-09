---
title: "Gewusst wie: Verwenden eines Ressourcenw&#246;rterbuchs f&#252;r den Anwendungsbereich | Microsoft Docs"
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
  - "Ressourcenwörterbücher für den Anwendungsbereich"
  - "Wörterbücher, Ressource"
  - "Ressourcenwörterbücher, Anwendungsbereich"
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Verwenden eines Ressourcenw&#246;rterbuchs f&#252;r den Anwendungsbereich
In diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Ressourcenwörterbuch für den Anwendungsbereich definiert und verwendet wird.  
  
## Beispiel  
 <xref:System.Windows.Application> macht einen Anwendungsbereichspeicher für freigegebene Ressourcen verfügbar: <xref:System.Windows.Application.Resources%2A>.  In der Standardeinstellung wird die <xref:System.Windows.Application.Resources%2A>\-Eigenschaft mit einer Instanz des <xref:System.Windows.ResourceDictionary>\-Typs initialisiert.  Sie verwenden diese Instanz, wenn Sie Eigenschaften für den Anwendungsbereich mit <xref:System.Windows.Application.Resources%2A> abrufen und festlegen.  \(Weitere Informationen finden Sie unter [How to: Get and Set an Application\-Scope Resource](http://msdn.microsoft.com/de-de/39e0420c-c9fc-47dc-8956-fdd95b214095).\)  
  
 Wenn Sie mehrere Ressourcen mit <xref:System.Windows.Application.Resources%2A> festlegen, können Sie diese auch in einem benutzerdefinierten Ressourcenwörterbuch speichern und <xref:System.Windows.Application.Resources%2A> damit festlegen.  Im Folgenden wird gezeigt, wie Sie mit XAML ein benutzerdefiniertes Ressourcenwörterbuch deklarieren.  
  
 [!code-xml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Die Möglichkeit des Austauschs kompletter Ressourcenwörterbücher mithilfe von <xref:System.Windows.Application.Resources%2A> erlaubt gleichzeitig die Verwendung von Designs für Anwendungsbereiche, die jeweils von einem einzigen Ressourcenwörterbuch gekapselt sind  Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.ResourceDictionary> veranschaulicht.  
  
 [!code-xml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Im Folgenden wird gezeigt, wie Sie Ressourcen für den Anwendungsbereich aus dem Ressourcenwörterbuch abrufen können, das von <xref:System.Windows.Application.Resources%2A> in XAML bereitgestellt wird.  
  
 [!code-xml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Im Folgenden wird gezeigt, wie Sie die Ressourcen auch in Code abrufen können.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Bei der Verwendung von <xref:System.Windows.Application.Resources%2A> müssen Sie zwei Punkte beachten.  Der Wörterbuch\-*Schlüssel* ist ein Objekt, deshalb müssen Sie genau dieselbe Objektinstanz verwenden, wenn Sie einen Eigenschaftswert festlegen und abrufen.  \(Beachten Sie, dass beim Verwenden einer Zeichenfolge beim Schlüssel die Groß\-\/Kleinschreibung beachtet wird.\) Zum anderen ist der Wörterbuch\-*Wert* ein Objekt. Daher müssen Sie den Wert beim Abrufen eines Eigenschaftswerts in den gewünschten Typ konvertieren.  
  
## Siehe auch  
 <xref:System.Windows.ResourceDictionary>   
 <xref:System.Windows.Application.Resources%2A>   
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Zusammengeführte Ressourcenwörterbücher](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)