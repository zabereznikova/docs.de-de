---
title: Verwendung des Serialisierungsbinders
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77f5c2914051c4310102a57b7181333bab6811b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="042f5-102">Verwendung des Serialisierungsbinders</span><span class="sxs-lookup"><span data-stu-id="042f5-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="042f5-103">In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="042f5-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="042f5-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="042f5-104">Demonstrates</span></span>  
 <span data-ttu-id="042f5-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="042f5-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="042f5-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="042f5-106">Discussion</span></span>  
 <span data-ttu-id="042f5-107">In diesem Beispiel wird gezeigt, wie zwei Entitäten, die andere [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen als Ziel haben, mit dem binären Formatierungsprogramm und dem Serialisierungsbinder kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="042f5-107">This sample shows how two entities that are targeting different versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="042f5-108">Dieses Beispiel wurde mit .NET-Remoting entwickelt.</span><span class="sxs-lookup"><span data-stu-id="042f5-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="042f5-109">Das Beispiel besteht aus einem Server mit der Zielversion [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], mit dem ein Vertrag mit generischen Typen implementiert wird, und zwei verschiedene Clients, einer mit der Zielversion [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] und einer mit der Zielversion [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="042f5-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="042f5-110">Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="042f5-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="042f5-111">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="042f5-111">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="042f5-112">Um den Client auszuführen, Maustaste die Projektmappe SBGenericsVTS (6 Projekte), und wählen Sie dann **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="042f5-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="042f5-113">In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie dann **mehrere Startprojekte**.</span><span class="sxs-lookup"><span data-stu-id="042f5-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="042f5-114">Wählen Sie **Server** zuerst, dann **Client20** und dann **Client40**.</span><span class="sxs-lookup"><span data-stu-id="042f5-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="042f5-115">Wählen Sie die **starten** Aktion für diese drei Projekte, und behalten Sie die restlichen festgelegt **keine**.</span><span class="sxs-lookup"><span data-stu-id="042f5-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4.  <span data-ttu-id="042f5-116">Klicken Sie auf **OK** und drücken Sie F5, um das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="042f5-116">Click **OK** and then press F5 to run the sample.</span></span>
