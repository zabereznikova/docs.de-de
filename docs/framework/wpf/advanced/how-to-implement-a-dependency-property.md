---
title: "Gewusst wie: Implementieren einer Abh&#228;ngigkeitseigenschaft | Microsoft Docs"
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
  - "Abhängigkeitseigenschaften, Sichern von Eigenschaften mit"
  - "Eigenschaften, Sichern mit Abhängigkeitseigenschaften"
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Implementieren einer Abh&#228;ngigkeitseigenschaft
Dieses Beispiel zeigt, wie Sie eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaft mit einem <xref:System.Windows.DependencyProperty>\-Feld unterstützen und auf diese Weise eine [Abhängigkeitseigenschaft](GTMT) definieren.  Wenn Sie Ihre eigenen Eigenschaften definieren und möchten, dass diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Funktionalität unterstützen, zum Beispiel Stile, Datenbindung, Vererbung, Animation und Standardwerte, sollten Sie die Eigenschaften als [Abhängigkeitseigenschaften](GTMT) implementieren.  
  
## Beispiel  
 Im folgenden Beispiel wird zuerst eine [Abhängigkeitseigenschaft](GTMT) registriert, indem die <xref:System.Windows.DependencyProperty.Register%2A>\-Methode aufgerufen wird.  Der Name des Bezeichnerfelds, das Sie zum Speichern des Namens und der Merkmale der [Abhängigkeitseigenschaft](GTMT) verwenden, muss der <xref:System.Windows.DependencyProperty.Name%2A> sein, den Sie für die Abhängigkeitseigenschaft als Teil des <xref:System.Windows.DependencyProperty.Register%2A>\-Aufrufs gewählt haben. Daran muss das Zeichenfolgenliteral `Property` angehängt werden.  Wenn Sie zum Beispiel eine Abhängigkeitseigenschaft mit dem <xref:System.Windows.DependencyProperty.Name%2A> `Location` registrieren, muss das Bezeichnerfeld, das Sie für die Abhängigkeitseigenschaft definieren, den Namen `LocationProperty` haben.  
  
 In diesem Beispiel lautet der Name der [Abhängigkeitseigenschaft](GTMT) und ihres [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Accessors `State`. Das Bezeichnerfeld ist `StateProperty`. Der Typ der Eigenschaft lautet <xref:System.Boolean>, und der Typ, der die [Abhängigkeitseigenschaft](GTMT) registriert, lautet `MyStateControl`.  
  
 Wenn Sie diese Konventionen der Namensgebung nicht befolgen, melden Designer Ihre Eigenschaft ggf. nicht richtig, und es kann sein, dass bestimmte Aspekte des Stilanwendungsmodus des Eigenschaftensystems sich nicht wie erwartet verhalten.  
  
 Sie können für eine [Abhängigkeitseigenschaft](GTMT) auch Standardmetadaten angeben.  Dieses Beispiel registriert den Standardwert der `State` [Abhängigkeitseigenschaft](GTMT) als `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Weitere Informationen dazu, wie und warum Sie eine [Abhängigkeitseigenschaft](GTMT) implementieren sollten, anstatt eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaft mit einem privaten Feld zu versehen, finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)