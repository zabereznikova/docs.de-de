---
title: 'Vorgehensweise: Verwenden der ChannelFactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: b407c76c86c7b4c988da5280d76c91969c155841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-channelfactory"></a>Vorgehensweise: Verwenden der ChannelFactory
Die generische <xref:System.ServiceModel.ChannelFactory%601>-Klasse wird in komplexen Szenarien verwendet, in denen eine Kanalfactory erstellt werden muss, die zum Erstellen mehrerer Kanäle eingesetzt werden kann.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>So erstellen und verwenden Sie die ChannelFactory-Klasse  
  
1.  Erstellen Sie und führen Sie einen Windows Communication Foundation (WCF)-Dienst. Weitere Informationen finden Sie unter [entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Konfigurieren von Services](../../../../docs/framework/wcf/configuring-services.md), und [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).  
  
2.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren des Vertrags (Schnittstelle) für den Client.  
  
3.  Verwenden Sie im Clientcode die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um mehrere Endpunktlistener zu erstellen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
