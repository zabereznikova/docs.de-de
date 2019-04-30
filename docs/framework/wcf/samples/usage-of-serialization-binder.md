---
title: Verwendung des Serialisierungsbinders
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 47a1974386927316ea9230ec27cf647d7245c44a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007590"
---
# <a name="usage-of-serialization-binder"></a>Verwendung des Serialisierungsbinders
In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird gezeigt, wie zwei Entitäten, die andere [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen als Ziel haben, mit dem binären Formatierungsprogramm und dem Serialisierungsbinder kommunizieren können.  
  
 Dieses Beispiel wurde mit .NET-Remoting entwickelt. Das Beispiel besteht aus einem Server mit der Zielversion [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], mit dem ein Vertrag mit generischen Typen implementiert wird, und zwei verschiedene Clients, einer mit der Zielversion [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] und einer mit der Zielversion [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1. Um den Client auszuführen, Maustaste die Projektmappe SBGenericsVTS (6 Projekte) und wählen Sie dann **Eigenschaften**.  
  
2. In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie dann **mehrere Startprojekte**.  
  
3. Wählen Sie **Server** zuerst, dann **Client20** und dann **Client40**. Wählen Sie die **starten** Aktion, die diese drei Projekte, und lassen Sie den Rest, legen Sie auf **keine**.  
  
4. Klicken Sie auf **OK** und drücken Sie F5, um das Beispiel auszuführen.
