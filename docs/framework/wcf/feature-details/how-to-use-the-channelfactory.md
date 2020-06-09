---
title: 'Vorgehensweise: Verwenden der ChannelFactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 4bb2053fb50931756e79d5346a3f14d2acbe04f6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595309"
---
# <a name="how-to-use-the-channelfactory"></a>Vorgehensweise: Verwenden der ChannelFactory
Die generische <xref:System.ServiceModel.ChannelFactory%601>-Klasse wird in komplexen Szenarien verwendet, in denen eine Kanalfactory erstellt werden muss, die zum Erstellen mehrerer Kanäle eingesetzt werden kann.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>So erstellen und verwenden Sie die ChannelFactory-Klasse  
  
1. Erstellen und Ausführen eines Windows Communication Foundation (WCF)-Dienstanbieter. Weitere Informationen finden Sie unter [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md), [Konfigurieren von Diensten](../configuring-services.md)und [Hostingdiensten](../hosting-services.md).  
  
2. Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um den Vertrag (Schnittstelle) für den Client zu generieren.  
  
3. Verwenden Sie im Clientcode die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um mehrere Endpunktlistener zu erstellen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
