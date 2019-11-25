---
title: Verwendung des Serialisierungsbinders
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: bfce2a14c8757250c520919c8ff2a4d7048a9d5c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138650"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="f84d6-102">Verwendung des Serialisierungsbinders</span><span class="sxs-lookup"><span data-stu-id="f84d6-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="f84d6-103">In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f84d6-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f84d6-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="f84d6-104">Demonstrates</span></span>  
 <span data-ttu-id="f84d6-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="f84d6-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="f84d6-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="f84d6-106">Discussion</span></span>  
 <span data-ttu-id="f84d6-107">Dieses Beispiel zeigt, wie zwei Entitäten, die auf unterschiedliche Versionen des .NET Framework abzielen, mit dem binären Formatierer und dem Serialisierungsbinder kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="f84d6-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="f84d6-108">Dieses Beispiel wurde mithilfe von .NET-Remoting entwickelt.</span><span class="sxs-lookup"><span data-stu-id="f84d6-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="f84d6-109">Sie besteht aus einem Server, der auf .NET Framework 4 abzielt, der einen Vertrag mit generischen Typen implementiert, und zwei verschiedenen Clients, von denen eine als Ziel .NET Framework 2,0 und eine andere als Ziel .NET Framework 4 ist.</span><span class="sxs-lookup"><span data-stu-id="f84d6-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="f84d6-110">Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="f84d6-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f84d6-111">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="f84d6-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="f84d6-112">Um den Client auszuführen, klicken Sie mit der rechten Maustaste auf die Projekt Mappe sbgenericsvts (6 Projekte), und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="f84d6-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="f84d6-113">Wählen Sie unter **Allgemeine Eigenschaften**die Option **Startprojekt**aus, und wählen Sie dann **mehrere Start Projekte**aus.</span><span class="sxs-lookup"><span data-stu-id="f84d6-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="f84d6-114">Wählen Sie zuerst **Server** , dann **Client20** und dann **Client40**aus.</span><span class="sxs-lookup"><span data-stu-id="f84d6-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="f84d6-115">Wählen Sie die Aktion **Start** für diese drei Projekte aus, und lassen Sie den Rest auf **keine**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f84d6-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="f84d6-116">Klicken Sie auf **OK** , und drücken Sie dann F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f84d6-116">Click **OK** and then press F5 to run the sample.</span></span>
