---
title: 'Gewusst wie: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich'
description: Erfahren Sie, wie Sie ein benutzerdefiniertes Ressourcen Wörterbuch im Anwendungsbereich in Windows Presentation Foundation (WPF) definieren und verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 9d117dea6c554339b4b462b9bf37b80da2dc477f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613708"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Gewusst wie: Verwenden eines Ressourcenwörterbuchs für den Anwendungsbereich
In diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Ressourcenverzeichnis für den Anwendungsbereich definiert und verwendet wird.  
  
## <a name="example"></a>Beispiel  
 <xref:System.Windows.Application>macht einen Anwendungsbereichs Speicher für freigegebene Ressourcen verfügbar: <xref:System.Windows.Application.Resources%2A> . Standardmäßig wird die- <xref:System.Windows.Application.Resources%2A> Eigenschaft mit einer Instanz des-Typs initialisiert <xref:System.Windows.ResourceDictionary> . Diese Instanz wird verwendet, wenn Sie mithilfe von Eigenschaften für den Anwendungsbereich erhalten und festlegen <xref:System.Windows.Application.Resources%2A> . Weitere Informationen finden Sie unter Gewusst [wie: Einrichten und Festlegen einer Ressource im Anwendungsbereich](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Wenn Sie über mehrere Ressourcen verfügen, die Sie mithilfe von festgelegt haben <xref:System.Windows.Application.Resources%2A> , können Sie stattdessen ein benutzerdefiniertes Ressourcen Wörterbuch verwenden, um diese Ressourcen zu speichern und stattdessen festzulegen <xref:System.Windows.Application.Resources%2A> . Das folgende Beispiel zeigt, wie Sie mit XAML ein benutzerdefiniertes Ressourcen Wörterbuch deklarieren.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Durch das austauschen ganzer Ressourcen Wörterbücher mithilfe <xref:System.Windows.Application.Resources%2A> von können Sie Anwendungsbereichs Designs unterstützen, wobei jedes Design von einem einzigen Ressourcen Wörterbuch gekapselt wird. Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.ResourceDictionary> veranschaulicht.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Im folgenden wird gezeigt, wie Sie Ressourcen im Anwendungsbereich aus dem Ressourcen Wörterbuch, das von verfügbar gemacht wird, <xref:System.Windows.Application.Resources%2A> in XAML erhalten.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Im Folgenden wird gezeigt, wie Sie die Ressourcen auch in Code abrufen können.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Bei der Verwendung von müssen zwei Aspekte berücksichtigt werden <xref:System.Windows.Application.Resources%2A> . Zuerst ist der Wörterbuch *Schlüssel* ein Objekt, sodass Sie genau dieselbe Objektinstanz verwenden müssen, wenn Sie einen Eigenschafts Wert festlegen und erhalten. (Beachten Sie, dass bei Verwendung einer Zeichenfolge beim Schlüssel die Groß-/Kleinschreibung beachtet wird.) Zweitens ist der Wörterbuch *Wert* ein Objekt, sodass Sie den Wert in den gewünschten Typ konvertieren müssen, wenn Sie einen Eigenschafts Wert erhalten.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Zusammengeführte Ressourcenwörterbücher](../advanced/merged-resource-dictionaries.md)
