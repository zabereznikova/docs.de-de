---
title: 'Gewusst wie: Verwenden von SystemFonts'
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
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce82724a4e9a547b8441628f43621f29eab6307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemfonts"></a>Gewusst wie: Verwenden von SystemFonts
In diesem Beispiel wird gezeigt, wie für die Verwendung der statischen Ressourcen von der <xref:System.Windows.SystemFonts> Klasse, um zu formatieren oder Anpassen einer Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, um visuelle Elemente zu erstellen, mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemFonts>ist eine Klasse, die beide System Schriftartwerte, als statische Eigenschaften und Eigenschaften, die auf Ressourcenschlüssel verweisen, die verwendet werden können enthält, um diese Werte dynamisch zur Laufzeit zugreifen. Beispielsweise <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ist ein <xref:System.Windows.SystemFonts> Wert und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ist ein entsprechender Ressourcenschlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemFonts> als Eigenschaften für statischen oder dynamischen Ressourcenverweise (mit der statischen Eigenschaft-Wert als Schlüssel). Verwenden Sie einen dynamischen Ressourcenverweis, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung automatisch aktualisieren soll; verwenden Sie andernfalls einen statischen Wertverweis.  
  
> [!NOTE]
>  Die Ressourcenschlüssel verfügen über das Suffix „Key“, das an den Eigenschaftennamen angefügt wird.  
  
 Im folgende Beispiel wird gezeigt, wie zugreifen auf und verwenden die Eigenschaften des <xref:System.Windows.SystemFonts> als statische Werte zum Formatieren oder Anpassen einer Schaltfläche. In diesem Markupbeispiel weist <xref:System.Windows.SystemFonts> Werte mit einer Schaltfläche.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Verwenden Sie die Werte der <xref:System.Windows.SystemFonts> in Code, Sie müssen nicht um einen statischen Wert oder einen dynamischen Ressourcenverweis zu verwenden. Verwenden Sie stattdessen die nicht schlüsselbezogene Eigenschaften von der <xref:System.Windows.SystemFonts> Klasse. Obwohl die nicht schlüsselbezogene Eigenschaften als statische Eigenschaften, die das Laufzeitverhalten des offensichtlich definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als gehostete durch das System wird neu Auswerten der Eigenschaften in Echtzeit und wird für Benutzer vorgenommene Änderungen Systemwerte ordnungsgemäß berücksichtigt. Im folgenden Beispiel wird veranschaulicht, wie die Schriftarteinstellung einer Schaltfläche festgelegt wird.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.SystemFonts>  
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Verwenden von SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [Verwenden von Systemschriftartschlüsseln](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [x:Statische Markuperweiterung](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
