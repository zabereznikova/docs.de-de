---
title: "Gewusst wie: Hinzuf&#252;gen eines Besitzertyps f&#252;r eine Abh&#228;ngigkeitseigenschaft | Microsoft Docs"
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
  - "Klassen, Hinzufügen von Eigentümern von Abhängigkeitseigenschaften"
  - "Abhängigkeitseigenschaften, Hinzufügen von Klassen als Eigentümer von"
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Hinzuf&#252;gen eines Besitzertyps f&#252;r eine Abh&#228;ngigkeitseigenschaft
In diesem Beispiel wird veranschaulicht, wie eine Klasse als Besitzer einer Abhängigkeitseigenschaft, die für einen anderen Typ registriert ist, hinzugefügt wird.  Hierdurch kann sowohl der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Reader als auch das Eigenschaftensystem die Klasse als weiteren Besitzer der Eigenschaft erkennen.  Das Hinzufügen als Besitzer ermöglicht optional auch das Hinzufügen der Klasse, damit typspezifische Metadaten bereitgestellt werden können.  
  
 Im folgenden Beispiel ist `StateProperty` eine der durch die `MyStateControl`\-Klasse registrierte Eigenschaft.  Die `UnrelatedStateControl`\-Klasse fügt sich selbst als ein Besitzer von `StateProperty` mithilfe der <xref:System.Windows.DependencyProperty.AddOwner%2A>\-Methode hinzu, wobei speziell die Signatur verwendet wird, die neue Metadaten für die Abhängigkeitseigenschaft, die im hinzufügenden Typ vorhanden sind, zulässt.  Beachten Sie, dass Sie [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Accessoren für die Eigenschaft bereitstellen müssen, ähnlich wie im Beispiel [Implementieren einer Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md), sowie die Kennung der Abhängigkeitseigenschaft für die Klasse, die als Besitzer hinzugefügt wird, erneut verfügbar machen müssen.  
  
 Ohne Wrapper funktioniert die Abhängigkeitseigenschaft aus der Sicht des programmgesteuerten Zugriffs mit <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A> trotzdem.  In der Regel soll das Verhalten dieses Eigenschaftensystems jedoch parallel zu den [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaftenwrappern sein.  Die Wrapper vereinfachen das programmgesteuerte Festlegen der Abhängigkeitseigenschaft und ermöglichen es, diese Eigenschaften als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Attribute festzulegen.  
  
 Informationen zum Überschreiben von Standardmetadaten finden Sie unter [Überschreiben von Metadaten für eine Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## Beispiel  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## Siehe auch  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)