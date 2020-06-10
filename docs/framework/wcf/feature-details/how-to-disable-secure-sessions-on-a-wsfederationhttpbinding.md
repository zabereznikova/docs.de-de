---
title: 'Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: df057d64feb89d1e43b938b36cb48f2f103b17d0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595387"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding

Für einige Dienste sind möglicherweise verbundene Anmeldeinformationen notwendig, sichere Sitzungen werden jedoch nicht unterstützt. In diesem Fall müssen Sie die Funktion für sichere Sitzungen deaktivieren. Im Gegensatz zu <xref:System.ServiceModel.WSHttpBinding> bietet die <xref:System.ServiceModel.WSFederationHttpBinding>-Klasse keinen Weg, um sichere Sitzungen bei der Kommunikation mit einem Dienst zu deaktivieren. Sie müssen vielmehr eine benutzerdefinierte Bindung erstellen, die die Einstellungen der sicheren Sitzung durch einen Bootstrap ersetzen.

In diesem Thema wird veranschaulicht, wie Sie das Bindungselement, das sich in einer <xref:System.ServiceModel.WSFederationHttpBinding> befindet, ändern können, um eine benutzerdefinierte Bindung zu erstellen. Das Ergebnis entspricht <xref:System.ServiceModel.WSFederationHttpBinding> mit Ausnahme der Tatsache, dass keine sicheren Sitzungen verwendet werden.

## <a name="to-create-a-custom-federated-binding-without-secure-session"></a>So erstellen Sie eine benutzerdefinierte Verbundbindung ohne sichere Sitzung

1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSFederationHttpBinding>-Klasse, sei es imperativ im Code oder durch das Laden einer Instanz aus der Konfigurationsdatei.

2. Klonen Sie <xref:System.ServiceModel.WSFederationHttpBinding> in <xref:System.ServiceModel.Channels.CustomBinding>.

3. Suchen Sie <xref:System.ServiceModel.Channels.SecurityBindingElement> in <xref:System.ServiceModel.Channels.CustomBinding>.

4. Suchen Sie <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in <xref:System.ServiceModel.Channels.SecurityBindingElement>.

5. Ersetzen Sie das ursprüngliche <xref:System.ServiceModel.Channels.SecurityBindingElement> durch das Bootstrap-Sicherheitsbindungselement aus <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.

## <a name="example"></a>Beispiel

Mit dem folgenden Beispielcode wird eine benutzerdefinierte Verbundbindung ohne sichere Sitzung erstellt.

[!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
[!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

- Um das Codebeispiel zu kompilieren, erstellen Sie ein Projekt, das auf die System.ServiceModel.dll-Assembly verweist.

## <a name="see-also"></a>Weitere Informationen

- [Bindungen und Sicherheit](bindings-and-security.md)
