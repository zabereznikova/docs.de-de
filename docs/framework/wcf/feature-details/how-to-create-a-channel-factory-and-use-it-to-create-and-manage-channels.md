---
title: 'Vorgehensweise: Erstellen einer Kanalfactory, mit der ein Kanal erstellt und verwaltet werden kann'
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 44b0f45d1a340b8e8229ded827ad3ded738ae677
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256780"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Vorgehensweise: Erstellen einer Kanalfactory, mit der ein Kanal erstellt und verwaltet werden kann

Die <xref:System.ServiceModel.DuplexChannelFactory%601>-Klasse ermöglicht das Erstellen und Verwalten von Duplexkanälen verschiedener Typen, die von Clients zum Senden und Empfangen von Nachrichten an bzw. von Dienstendpunkten verwendet werden.  
  
## <a name="example"></a>Beispiel  

 Der folgende Code zeigt, wie eine Kanalfactory erstellt und zum Erstellen und Verwalten von Kanälen verwendet wird.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.DuplexChannelFactory%601>
