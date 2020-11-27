---
title: 'Vorgehensweise: Verwenden mehrerer Sicherheitstokens desselben Typs'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 7374eebb9e42ef761b7ab8980b3eacf4d5671e6d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280701"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Vorgehensweise: Verwenden mehrerer Sicherheitstokens desselben Typs

- In .NET Framework 3,0 enthielt eine Client Nachricht nur ein Token eines beliebigen Typs. Jetzt können Clientnachrichten mehrere Token eines Typs enthalten. In diesem Thema wird das Einfügen mehrerer Token desselben Typs in eine Clientnachricht erläutert.  
  
- Ein Dienst kann nicht auf diese Weise konfiguriert werden, da ein Dienst lediglich ein einzelnes unterstützendes Token enthalten kann.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>Gewusst wie: Verwenden mehrerer Sicherheitstokens desselben Typs  
  
1. Erstellen Sie eine leere auszufüllende Bindungselementauflistung.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2. Erstellen Sie <xref:System.ServiceModel.Channels.SecurityBindingElement> durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3. Erstellen Sie eine <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>-Auflistung.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4. Fügen Sie der Auflistung SAML-Tokens hinzu.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5. Fügen Sie die Auflistung <xref:System.ServiceModel.Channels.SecurityBindingElement> hinzu.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6. Fügen Sie der Bindungselementauflistung Bindungselemente hinzu.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7. Geben Sie aus der Bindungselementauflistung eine neue benutzerdefinierte Bindung zurück.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>Beispiel  

 Nachfolgend ist die gesamte Methode aufgeführt, die durch die vorherige Prozedur beschrieben wird.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
