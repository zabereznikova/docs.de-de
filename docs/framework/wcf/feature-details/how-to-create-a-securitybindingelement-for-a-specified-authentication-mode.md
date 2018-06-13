---
title: 'Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 70c3e371be3af5f03ea85f1681155c2590d42373
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489530"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a>Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus
Windows Communication Foundation (WCF) stellt verschiedene Modi, die durch die Clients und Dienste gegenseitig authentifizieren. Sie können Sicherheitsbindungselemente für diese Authentifizierungsmodi erstellen. Dazu verwenden Sie statische Methoden für die <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse oder die Konfiguration, wie im folgenden Beispiel dargestellt.  
  
 Weitere Informationen über die 18 Authentifizierungsmodi finden Sie unter [SecurityBindingElement-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden Methoden zum Erstellen von Bindungen für die verschiedenen Authentifizierungsmodi veranschaulicht.  
  
> [!NOTE]
>  Nachdem eine Instanz des <xref:System.ServiceModel.Channels.SecurityBindingElement>-Objekts erstellt wurde, sind einige Eigenschaften unveränderlich, wie beispielsweise <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> und <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>. `set` für diese Eigenschaften aufzurufen, hat keinen Effekt.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [SecurityBindingElement-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
