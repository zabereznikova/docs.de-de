---
title: Verwendung des Serialisierungsbinders
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 47a1974386927316ea9230ec27cf647d7245c44a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329842"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="2a4d4-102">Verwendung des Serialisierungsbinders</span><span class="sxs-lookup"><span data-stu-id="2a4d4-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="2a4d4-103">In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2a4d4-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="2a4d4-104">Demonstrates</span></span>  
 <xref:System.Runtime.Serialization.SerializationBinder><span data-ttu-id="2a4d4-105">,</span><span class="sxs-lookup"><span data-stu-id="2a4d4-105">,</span></span> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a><span data-ttu-id="2a4d4-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="2a4d4-106">Discussion</span></span>  
 <span data-ttu-id="2a4d4-107">In diesem Beispiel wird gezeigt, wie zwei Entitäten, die andere [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen als Ziel haben, mit dem binären Formatierungsprogramm und dem Serialisierungsbinder kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-107">This sample shows how two entities that are targeting different versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="2a4d4-108">Dieses Beispiel wurde mit .NET-Remoting entwickelt.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="2a4d4-109">Das Beispiel besteht aus einem Server mit der Zielversion [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], mit dem ein Vertrag mit generischen Typen implementiert wird, und zwei verschiedene Clients, einer mit der Zielversion [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] und einer mit der Zielversion [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a4d4-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="2a4d4-110">Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a4d4-111">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="2a4d4-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="2a4d4-112">Um den Client auszuführen, Maustaste die Projektmappe SBGenericsVTS (6 Projekte) und wählen Sie dann **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="2a4d4-113">In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie dann **mehrere Startprojekte**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="2a4d4-114">Wählen Sie **Server** zuerst, dann **Client20** und dann **Client40**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="2a4d4-115">Wählen Sie die **starten** Aktion, die diese drei Projekte, und lassen Sie den Rest, legen Sie auf **keine**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="2a4d4-116">Klicken Sie auf **OK** und drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-116">Click **OK** and then press F5 to run the sample.</span></span>
