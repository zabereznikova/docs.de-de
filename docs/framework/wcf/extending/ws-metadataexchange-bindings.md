---
title: WS-MetadataExchange-Bindungen
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795472"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="d3ced-102">WS-MetadataExchange-Bindungen</span><span class="sxs-lookup"><span data-stu-id="d3ced-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="d3ced-103">In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch-Bindungen für verschiedene Transporte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d3ced-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="d3ced-104">Die Standardbindungen</span><span class="sxs-lookup"><span data-stu-id="d3ced-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="d3ced-105">Standardbindungsname</span><span class="sxs-lookup"><span data-stu-id="d3ced-105">Default Binding Name</span></span>|<span data-ttu-id="d3ced-106">Wie die Bindung erstellt wird</span><span class="sxs-lookup"><span data-stu-id="d3ced-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="d3ced-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d3ced-107">mexHttpBinding</span></span>|<span data-ttu-id="d3ced-108">Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.</span><span class="sxs-lookup"><span data-stu-id="d3ced-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="d3ced-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="d3ced-109">mexHttpsBinding</span></span>|<span data-ttu-id="d3ced-110">Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3ced-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="d3ced-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="d3ced-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="d3ced-112">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3ced-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="d3ced-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="d3ced-113">mexTcpBinding</span></span>|<span data-ttu-id="d3ced-114">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3ced-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
