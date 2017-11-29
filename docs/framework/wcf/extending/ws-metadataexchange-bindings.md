---
title: WS-MetadataExchange-Bindungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 23752cb259accb1df6093a4b1d90a2541fd771d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="812a4-102">WS-MetadataExchange-Bindungen</span><span class="sxs-lookup"><span data-stu-id="812a4-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="812a4-103">In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch-Bindungen für verschiedene Transporte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="812a4-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="812a4-104">Die Standardbindungen</span><span class="sxs-lookup"><span data-stu-id="812a4-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="812a4-105">Standardbindungsname</span><span class="sxs-lookup"><span data-stu-id="812a4-105">Default Binding Name</span></span>|<span data-ttu-id="812a4-106">Wie die Bindung erstellt wird</span><span class="sxs-lookup"><span data-stu-id="812a4-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="812a4-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="812a4-107">MexHttpBinding</span></span>|<span data-ttu-id="812a4-108">Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.</span><span class="sxs-lookup"><span data-stu-id="812a4-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="812a4-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="812a4-109">MexHttpsBinding</span></span>|<span data-ttu-id="812a4-110">Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="812a4-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="812a4-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="812a4-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="812a4-112">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="812a4-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="812a4-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="812a4-113">MexTcpBinding</span></span>|<span data-ttu-id="812a4-114">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="812a4-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
