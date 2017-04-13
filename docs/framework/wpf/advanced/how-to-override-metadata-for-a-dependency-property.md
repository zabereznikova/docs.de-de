---
title: "Gewusst wie: &#220;berschreiben von Metadaten f&#252;r eine Abh&#228;ngigkeitseigenschaft | Microsoft Docs"
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
  - "Abhängigkeitseigenschaften, Überschreiben von Metadaten für"
  - "Metadaten, Überschreiben für Abhängigkeitseigenschaften"
  - "Überschreiben von Metadaten für Abhängigkeitseigenschaften"
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: &#220;berschreiben von Metadaten f&#252;r eine Abh&#228;ngigkeitseigenschaft
In diesem Beispiel wird veranschaulicht, wie die standardmäßigen Metadaten für die Abhängigkeitseigenschaft einer geerbten Klasse überschrieben werden, indem die <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>\-Methode aufgerufen wird und typspezifische Metadaten bereitgestellt werden.  
  
## Beispiel  
 Durch die Definition der <xref:System.Windows.PropertyMetadata> kann eine Klasse die Verhalten einer [Abhängigkeitseigenschaft](GTMT) definieren, wie z. B. deren Standardwert und Rückrufe des Eigenschaftensystems.  Viele Abhängigkeitseigenschaftenklassen verfügen bereits über Standardmetadaten als Teil ihres Registrierungsprozesses.  Hierzu gehören die Abhängigkeitseigenschaften, die Teil von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] sind.  Eine Klasse, die die Abhängigkeitseigenschaft über ihre Klassenvererbung erbt, kann die ursprünglichen Metadaten überschreiben, sodass die Eigenschaftenmerkmale, die über Metadaten geändert werden können, eventuellen unterklassenspezifischen Anforderungen entsprechen.  
  
 Das Überschreiben von Metadaten für eine Abhängigkeitseigenschaft muss durchgeführt werden, bevor die betreffende Eigenschaft für die Verwendung im Eigenschaftensystem verfügbar gemacht wird \(dies entspricht dem Zeitpunkt, zu dem bestimmte Instanzen von Objekten instanziiert werden, die die Eigenschaft registrieren\).  Aufrufe von <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> müssen in den statischen Konstruktoren des Typs ausgeführt werden, der sich selbst als `forType`\-Parameter von <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> bereitstellt.  Durch den Versuch, Metadaten zu ändern, nachdem Instanzen des Besitzertyps vorhanden sind, werden keine Ausnahmen ausgelöst. Dies führt jedoch zu inkonsistentem Verhalten im Eigenschaftensystem.  Außerdem können Metadaten nur einmal pro Typ überschrieben werden.  Nachfolgende Versuche, Metadaten für den gleichen Typ zu überschreiben, lösen eine Ausnahme aus.  
  
 Im folgenden Beispiel überschreibt die benutzerdefinierte `MyAdvancedStateControl`\-Klasse die für die `StateProperty` von `MyAdvancedStateControl` bereitgestellten Metadaten mit neuen Eigenschaftenmetadaten.  Der Standardwert der `StateProperty` ist z. B. jetzt `true`, wenn die Eigenschaft für eine neu erstellte `MyAdvancedStateControl`\-Instanz abgefragt wird.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## Siehe auch  
 <xref:System.Windows.DependencyProperty>   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)