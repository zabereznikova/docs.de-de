---
title: Bindungserweiterbarkeit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13f17264aa1c82f882d799e6b69a974e8abdb133
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="binding-extensibility"></a><span data-ttu-id="2cefa-102">Bindungserweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="2cefa-102">Binding Extensibility</span></span>

<span data-ttu-id="2cefa-103">Dieser Abschnitt enthält Beispiele, in denen die benutzerdefinierte Bindung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] demonstriert wird.</span><span class="sxs-lookup"><span data-stu-id="2cefa-103">This section contains samples that demonstrate custom binding in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cefa-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2cefa-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="2cefa-105">Veranschaulicht, wie eine Bindung implementiert wird, bei der das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> oder das <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> über das <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> gestapelt wird.</span><span class="sxs-lookup"><span data-stu-id="2cefa-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="2cefa-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2cefa-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="2cefa-107">Veranschaulicht das Erstellen einer Bindung, die Streamingszenarios unterstützt, wenn HTTP-Transport verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cefa-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
