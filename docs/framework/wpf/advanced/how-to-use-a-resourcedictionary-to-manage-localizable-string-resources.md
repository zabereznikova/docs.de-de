---
title: 'Vorgehensweise: Verwalten lokalisierbarer Zeichenfolgenressourcen mit einem ResourceDictionary'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: e28086d8c97070b854ebdea35fe347c64c5cd7ac
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377936"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Vorgehensweise: Verwalten lokalisierbarer Zeichenfolgenressourcen mit einem ResourceDictionary
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.ResourceDictionary> zum Paket lokalisierbarer Zeichenfolgenressourcen für Windows Presentation Foundation (WPF)-Anwendungen.  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>So verwenden Sie ResourceDictionary zum Verwalten lokalisierbarer Zeichenfolgenressourcen  
  
1.  Erstellen Sie eine <xref:System.Windows.ResourceDictionary> , enthält die Zeichenfolgen, die Sie lokalisieren möchten. Der folgende Code zeigt ein Beispiel.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Dieser Code definiert eine Zeichenfolgenressource `localizedMessage`, des Typs <xref:System.String>, aus der <xref:System> Namespace in "mscorlib.dll".  
  
2.  Hinzufügen der <xref:System.Windows.ResourceDictionary> an Ihre Anwendung mithilfe des folgenden Codes.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Verwenden Sie die Zeichenfolge vom Markup mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wie im folgenden Beispiel.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Verwenden Sie die Zeichenfolge von CodeBehind mithilfe von Code so wie folgt.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Lokalisieren Sie die Anwendung. Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).
