---
title: "Gewusst wie: Verwenden von Systemschriftartschlüsseln"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 53538c64d2af5d8407f79848ddcd01f7665303c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-fonts-keys"></a>Gewusst wie: Verwenden von Systemschriftartschlüsseln
Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemFonts>ist eine Klasse, die Schriftart Systemwerte und Schriftart Systemressourcen, die an die Werte binden enthält – z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden. Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.  
  
> [!NOTE]
>  Dynamische Ressourcen ist das Schlüsselwort *Schlüssel* des Eigenschaftennamens angefügt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen. Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt eine Vorlage, die weist <xref:System.Windows.SystemFonts> Werte mit einer Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Verwenden von SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [Verwenden von SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
