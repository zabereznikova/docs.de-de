---
title: 'Gewusst wie: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459796"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Gewusst wie: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich
In diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Ressourcenverzeichnis für den Anwendungsbereich definiert und verwendet wird.  
  
## <a name="example"></a>Beispiel  
 <xref:System.Windows.Application> macht einen Anwendungsbereichs Speicher für freigegebene Ressourcen verfügbar: <xref:System.Windows.Application.Resources%2A>. Standardmäßig wird die <xref:System.Windows.Application.Resources%2A>-Eigenschaft mit einer Instanz des <xref:System.Windows.ResourceDictionary> Typs initialisiert. Diese Instanz wird verwendet, wenn Sie mithilfe von <xref:System.Windows.Application.Resources%2A>Eigenschaften für den Anwendungsbereich erhalten und festlegen. Weitere Informationen finden Sie unter Gewusst [wie: Einrichten und Festlegen einer Ressource im Anwendungsbereich](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Wenn Sie über mehrere Ressourcen verfügen, die Sie mit <xref:System.Windows.Application.Resources%2A>festlegen, können Sie stattdessen ein benutzerdefiniertes Ressourcen Wörterbuch verwenden, um diese Ressourcen zu speichern und <xref:System.Windows.Application.Resources%2A> stattdessen darauf festzulegen. Das folgende Beispiel zeigt, wie Sie mit XAML ein benutzerdefiniertes Ressourcen Wörterbuch deklarieren.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Durch das austauschen ganzer Ressourcen Wörterbücher mithilfe von <xref:System.Windows.Application.Resources%2A> können Sie Themen im Anwendungsbereich unterstützen, wobei jedes Design von einem einzigen Ressourcen Wörterbuch gekapselt wird. Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.ResourceDictionary> veranschaulicht.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Das folgende Beispiel zeigt, wie Sie Ressourcen im Anwendungsbereich aus dem Ressourcen Wörterbuch, das von <xref:System.Windows.Application.Resources%2A> in XAML verfügbar gemacht wird, erhalten können.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Im Folgenden wird gezeigt, wie Sie die Ressourcen auch in Code abrufen können.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Bei der Verwendung von <xref:System.Windows.Application.Resources%2A>müssen zwei Aspekte berücksichtigt werden. Zuerst ist der Wörterbuch *Schlüssel* ein Objekt, sodass Sie genau dieselbe Objektinstanz verwenden müssen, wenn Sie einen Eigenschafts Wert festlegen und erhalten. (Beachten Sie, dass bei Verwendung einer Zeichenfolge beim Schlüssel die Groß-/Kleinschreibung beachtet wird.) Zweitens ist der Wörterbuch *Wert* ein Objekt, sodass Sie den Wert in den gewünschten Typ konvertieren müssen, wenn Sie einen Eigenschafts Wert erhalten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Zusammengeführte Ressourcenverzeichnisse](../advanced/merged-resource-dictionaries.md)
