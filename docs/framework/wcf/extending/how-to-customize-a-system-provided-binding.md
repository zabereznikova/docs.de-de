---
title: 'Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9b048b5c57d174ac921793ee8677622b88a0595
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-a-system-provided-binding"></a>Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] umfasst mehrere systemseitig bereitgestellte Bindungen, bei denen Sie einige der Eigenschaften von zugrundeliegenden Bindungselementen konfigurieren können. Es lassen sich jedoch nicht alle Eigenschaften konfigurieren. In diesem Thema wird veranschaulicht, wie Sie Eigenschaften für die Bindungselemente festlegen, um eine benutzerdefinierte Bindung zu erstellen.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]zum direkt zu erstellen und konfigurieren Sie Bindungselemente, ohne mit den vom System bereitgestellte Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erstellen und Erweitern von benutzerdefinierten Bindungen finden Sie unter [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Alle Bindungen bestehen aus *Bindungselementen*. Jedes Bindungselement wird von der <xref:System.ServiceModel.Channels.BindingElement>-Klasse abgeleitet. Systemseitig bereitgestellte Bindungen wie <xref:System.ServiceModel.BasicHttpBinding> erstellen und konfigurieren ihre eigenen Bindungselemente. In diesem Thema wird gezeigt, wie Sie auf die Eigenschaften dieser Bindungselemente zugreifen und sie ändern können. Die Elemente sind nicht direkt über die Bindung verfügbar. Dies trifft insbesondere auf die <xref:System.ServiceModel.BasicHttpBinding>-Klasse zu.  
  
 Die einzelnen Bindungselemente sind in einer Auflistung, die von der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse dargestellt wird, enthalten, und werden in dieser Reihenfolge hinzugefügt: Transaktionsfluss, zuverlässige Sitzung, Sicherheit, Composite Duplex, Eindirektional, Streamsicherheit, Nachrichtencodierung und Transport. Beachten Sie, dass nicht alle aufgelisteten Bindungselemente in jeder Bindung erforderlich sind. Auch benutzerdefinierte Bindungselemente können in dieser Auflistung enthalten sein und müssen in der gerade beschriebenen Reihenfolge angezeigt werden. Zum Beispiel muss ein benutzerdefinierter Transport das letzte Element der Bindungselementeauflistung sein.  
  
 Die <xref:System.ServiceModel.BasicHttpBinding>-Klasse enthält drei Bindungselemente:  
  
1.  Ein optionales Sicherheitsbindungselement, entweder die beim HTTP-Transport verwendete <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>-Klasse (Sicherheit auf Nachrichtenebene) oder die <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>-Klasse, die verwendet wird, wenn die Transportschicht für die Sicherheit sorgt. In diesem Fall wird der HTTPS-Transport verwendet.  
  
2.  Ein erforderliches Bindungselement zur Nachrichtencodierung, entweder <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> oder <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
3.  Ein erforderliches Transportbindungselement, entweder <xref:System.ServiceModel.Channels.HttpTransportBindingElement> oder <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
 Wir in diesem Beispiel erstellen Sie eine Instanz der Bindung, generieren eine *benutzerdefinierte Bindung* aus, die Bindungselemente der benutzerdefinierten Bindung untersucht und wenn das HTTP-Bindungselement gefunden wird, legen wir die `KeepAliveEnabled` Eigenschaft `false`. Die `KeepAliveEnabled`-Eigenschaft steht nicht direkt über die `BasicHttpBinding` zur Verfügung, sodass eine benutzerdefinierte Bindung erstellt werden muss, um zum Bindungselement zu navigieren und dessen Eigenschaft festzulegen.  
  
### <a name="to-modify-a-system-provided-binding"></a>So ändern Sie eine vom System bereitgestellte Bindung  
  
1.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.BasicHttpBinding>-Klasse und legen Sie ihren Sicherheitsmodus auf die Nachrichtenebene fest.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  Erstellen Sie eine benutzerdefinierte Bindung aus dieser Bindung, und erstellen Sie eine <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse aus einer der Eigenschaften der benutzerdefinierten Bindung.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  Durchlaufen Sie die <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse, und wenn Sie die <xref:System.ServiceModel.Channels.HttpTransportBindingElement>-Klasse gefunden haben, legen Sie deren <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A>-Eigenschaft auf `false` fest.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)
