---
title: "Gewusst wie: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 417fea4dcbb5a8d0a27f9605be19de5921aaf0ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Gewusst wie: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich
In diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Ressourcenverzeichnis für den Anwendungsbereich definiert und verwendet wird.  
  
## <a name="example"></a>Beispiel  
 <xref:System.Windows.Application>Stellt ein Anwendungsbereich speichert freigegebene Ressourcen: <xref:System.Windows.Application.Resources%2A>. Wird standardmäßig die <xref:System.Windows.Application.Resources%2A> -Eigenschaft wird mit einer Instanz von initialisiert die <xref:System.Windows.ResourceDictionary> Typ. Sie verwenden diese Instanz, wenn Sie abrufen und Festlegen des Anwendungsumfangs Eigenschaften, die mit <xref:System.Windows.Application.Resources%2A>. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen und Festlegen von eine anwendungsspezifische Ressource](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).
  
 Wenn Sie mehrere Ressourcen, die Sie festlegen verfügen, über <xref:System.Windows.Application.Resources%2A>, stattdessen können Sie ein benutzerdefiniertes Ressourcenverzeichnis speichern, und legen Sie <xref:System.Windows.Application.Resources%2A> mit ihm stattdessen. Das folgende Beispiel zeigt, wie Sie ein benutzerdefiniertes Ressourcenwörterbuch mit XAML deklarieren.
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Austauschen der gesamten Ressourcendatenbank Wörterbüchern unter Verwendung von <xref:System.Windows.Application.Resources%2A> bietet die Möglichkeit, Anwendungsbereich Designs, zu unterstützen, in dem jedes Design von einem einzigen Ressourcenwörterbuch gekapselt wird. Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.ResourceDictionary> veranschaulicht.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Im folgenden wird gezeigt, wie Sie Anwendungsbereich Ressourcen aus dem Ressourcenwörterbuch abrufen können <xref:System.Windows.Application.Resources%2A> in XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Im Folgenden wird gezeigt, wie Sie die Ressourcen auch in Code abrufen können.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Es gibt zwei Aspekte, die bei der Verwendung <xref:System.Windows.Application.Resources%2A>. Zuerst wird das Wörterbuch *Schlüssel* ist ein Objekt, sodass Sie genau die gleiche Objektinstanz beim Festlegen und Abrufen eines Eigenschaftswerts verwenden müssen. (Beachten Sie, dass beim Verwenden einer Zeichenfolge beim Schlüssel die Groß-/Kleinschreibung beachtet wird.) Sekunde, die dem Wörterbuch *Wert* ist ein Objekt, daher Sie den Wert in den gewünschten Typ zu konvertieren, wenn Sie einen Eigenschaftswert abrufen müssen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Zusammengeführte Ressourcenverzeichnisse](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
