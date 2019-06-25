---
title: Verwendung des Serialisierungsbinders
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 10900950b935b484053fe8e37263f0dfc25eba99
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348460"
---
# <a name="usage-of-serialization-binder"></a>Verwendung des Serialisierungsbinders
In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Diskussion  
 Dieses Beispiel zeigt wie zwei Entitäten, sind mit verschiedene Versionen von .NET Framework können kommunizieren mit dem binären Formatierungsprogramm und dem Serialisierungsbinder.  
  
Dieses Beispiel wurde die Verwendung von .NET-Remoting entwickelt. Es besteht aus einem Server für die Zielgruppenadressierung [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], implementiert einen Vertrag mit generischen Typen und zwei verschiedene Clients, eine auf .NET Framework 2.0 und einer mit der Zielversion [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1. Um den Client auszuführen, Maustaste die Projektmappe SBGenericsVTS (6 Projekte) und wählen Sie dann **Eigenschaften**.  
  
2. In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie dann **mehrere Startprojekte**.  
  
3. Wählen Sie **Server** zuerst, dann **Client20** und dann **Client40**. Wählen Sie die **starten** Aktion, die diese drei Projekte, und lassen Sie den Rest, legen Sie auf **keine**.  
  
4. Klicken Sie auf **OK** und drücken Sie F5, um das Beispiel auszuführen.
