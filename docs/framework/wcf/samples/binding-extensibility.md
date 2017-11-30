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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 251d89af938b4bf104ddb86689b2573856386d75
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="binding-extensibility"></a><span data-ttu-id="c5373-102">Bindungserweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="c5373-102">Binding Extensibility</span></span>

<span data-ttu-id="c5373-103">Dieser Abschnitt enthält Beispiele, in denen die benutzerdefinierte Bindung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] demonstriert wird.</span><span class="sxs-lookup"><span data-stu-id="c5373-103">This section contains samples that demonstrate custom binding in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5373-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c5373-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="c5373-105">Veranschaulicht, wie eine Bindung implementiert wird, bei der das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> oder das <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> über das <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> gestapelt wird.</span><span class="sxs-lookup"><span data-stu-id="c5373-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="c5373-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c5373-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="c5373-107">Veranschaulicht das Erstellen einer Bindung, die Streamingszenarios unterstützt, wenn HTTP-Transport verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5373-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
