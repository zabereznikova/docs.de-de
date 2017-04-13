---
title: "PresentationOptions:Freeze-Attribut | Microsoft Docs"
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
  - "Freezable-Elemente"
  - "Freeze-Attribut"
  - "PresentationOptions-Präfix"
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# PresentationOptions:Freeze-Attribut
Legt den <xref:System.Windows.Freezable.IsFrozen%2A>\-Zustand im enthaltenden <xref:System.Windows.Freezable>\-Element auf `true` fest.  Als Standardverhalten von <xref:System.Windows.Freezable> ohne Angabe des `PresentationOptions:Freeze`\-Attributs gilt: <xref:System.Windows.Freezable.IsFrozen%2A> ist bei Ladezeit `false` und vom allgemeinen <xref:System.Windows.Freezable>\-Verhalten zur Laufzeit abhängig.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`PresentationOptions`|Ein XML\-Namespace, der jede gültige Präfixzeichenfolge gemäß der XML 1.0\-Spezifikation sein kann.  Das Präfix `PresentationOptions` wird in dieser Dokumentation für Identifikationszwecke verwendet.|  
|`freezableElement`|Ein Element, das jede abgeleitete Klasse von <xref:System.Windows.Freezable> instanziiert.|  
  
## Hinweise  
 Das `Freeze`\-Attribut ist das einzige Attribut oder ein anderes, im `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML\-Namespace definiertes Element.  Das `Freeze`\-Attribut ist in diesem speziellen Namespace spezifisch so vorhanden, dass es als ignorierbar bezeichnet werden kann. [mc:Ignorable\-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) wird als Teil der Stammelementdeklarationen verwendet.  Der Grund, aus dem `Freeze` ignorierbar sein können muss, liegt darin, dass alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessorimplementierungen in der Lage sind, ein <xref:System.Windows.Freezable> bei Ladezeit zu sperren. Diese Fähigkeit ist nicht Teil der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Spezifikation.  
  
 Die Möglichkeit zur Verarbeitung des `Freeze`\-Attributs ist speziell in den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor integriert, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für kompilierte Anwendungen verarbeitet.  Das Attribut wird von keiner Klasse unterstützt, und die Attributsyntax ist nicht erweiterbar oder änderbar.  Wenn Sie einen eigenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor implementieren, können Sie festlegen, dass das Sperrverhalten des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessors beim Verarbeiten des `Freeze`\-Attributes für <xref:System.Windows.Freezable>\-Elemente bei Ladezeit entsprechend ist.  
  
 Wenn das `Freeze`\-Attribut einen anderen Wert als `true` \(ohne Beachtung von Groß\-\/Kleinschreibung\) hat, wird ein Ladezeitfehler generiert.  \(Wenn für das `Freeze`\-Attribut der Wert `false` angegeben wird, so ist das kein Fehler, sondern bereits die Standardeinstellung, d. h. die Einstellung auf `false` hat keine Wirkung\).  
  
## Siehe auch  
 <xref:System.Windows.Freezable>   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [mc:Ignorable\-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)