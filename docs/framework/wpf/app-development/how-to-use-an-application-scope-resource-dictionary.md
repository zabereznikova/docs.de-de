---
title: 'Vorgehensweise: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 6cd3e125b5b1a97f5851d4d1845e3e9e384e3d16
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748556"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Vorgehensweise: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich
In diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Ressourcenverzeichnis für den Anwendungsbereich definiert und verwendet wird.  
  
## <a name="example"></a>Beispiel  
 <xref:System.Windows.Application> macht einen Anwendungsbereichspeicher für freigegebene Ressourcen: <xref:System.Windows.Application.Resources%2A>. In der Standardeinstellung die <xref:System.Windows.Application.Resources%2A> -Eigenschaft wird mit einer Instanz von initialisiert die <xref:System.Windows.ResourceDictionary> Typ. Sie verwenden diese Instanz, wenn Sie abrufen und Festlegen von Eigenschaften für den Anwendungsbereich über <xref:System.Windows.Application.Resources%2A>. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen und festlegen eine Ressource für den Anwendungsbereich](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Wenn Sie mehrere Ressourcen, die Sie festlegen, über <xref:System.Windows.Application.Resources%2A>, Sie können stattdessen ein benutzerdefiniertes Ressourcenverzeichnis verwenden, um diese Ressourcen zu speichern, und legen Sie <xref:System.Windows.Application.Resources%2A> mit stattdessen. Das folgende Beispiel zeigt, wie Sie ein benutzerdefiniertes Ressourcenverzeichnis mit XAML deklarieren.
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Kompletter Ressourcenverzeichnisse mithilfe von <xref:System.Windows.Application.Resources%2A> ermöglicht es Ihnen, die für den Anwendungsbereich Designs für Anwendungsbereiche, die jeweils von einem einzigen Ressourcenverzeichnis gekapselt ist. Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.ResourceDictionary> veranschaulicht.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Das folgende Beispiel zeigt, wie Sie für den Anwendungsbereich-Ressourcen aus dem Ressourcenverzeichnis verfügbar gemacht werden, indem abrufen können <xref:System.Windows.Application.Resources%2A> in XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Im Folgenden wird gezeigt, wie Sie die Ressourcen auch in Code abrufen können.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Es gibt zwei Überlegungen, die bei der Verwendung <xref:System.Windows.Application.Resources%2A>. Zuerst wird das Wörterbuch *Schlüssel* ist ein Objekt, aus, sodass Sie genau die gleiche Objektinstanz beim Festlegen und Abrufen eines Eigenschaftswerts verwenden müssen. (Beachten Sie, dass beim Verwenden einer Zeichenfolge beim Schlüssel die Groß-/Kleinschreibung beachtet wird.) Anderen ist der *Wert* ist ein Objekt, aus, sodass Sie den Wert in den gewünschten Typ zu konvertieren, wenn einen Eigenschaftswert abgerufen werden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Zusammengeführte Ressourcenverzeichnisse](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
