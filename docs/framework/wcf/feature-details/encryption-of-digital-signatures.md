---
title: Verschlüsselung von digitalen Signaturen
ms.date: 03/30/2017
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
ms.openlocfilehash: dece961ac70dbcf310e5e4a9dcb05c303c787ad4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251437"
---
# <a name="encryption-of-digital-signatures"></a>Verschlüsselung von digitalen Signaturen

Standardmäßig wird eine Nachricht signiert und verschlüsselt, und die Signatur wird digital verschlüsselt. Dies können Sie steuern, indem Sie eine benutzerdefinierte Bindung mit einer Instanz von <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> erstellen und dann die `MessageProtectionOrder`-Eigenschaft der Klasse auf einen <xref:System.ServiceModel.Security.MessageProtectionOrder>-Enumerationswert festlegen. Der Standardwert ist <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Im Vergleich zum einfachen Signieren und Verschlüsseln dauert dieser Prozess 10 bis 40&#160;Prozent länger. Wenn Sie die Verschlüsselung der Signatur jedoch deaktivieren, kann ein Angreifer eventuell den Inhalt der Nachricht erraten. Dies ist möglich, da das Signaturelement den Hashcode des reinen Texts des signierten Teils der Nachricht enthält. Obwohl der Nachrichtentext zwar standardmäßig verschlüsselt ist, enthält die unverschlüsselte Signatur z.&#160;B. den Hashcode des Nachrichtentexts. Wenn die Nachricht klein ist, könnte ein Angreifer den Inhalt herleiten. Diese Möglichkeit wird durch das Verschlüsseln der Signatur reduziert oder ausgeschlossen.  
  
 Deshalb sollten Sie die Verschlüsselung der Signatur nur deaktivieren, wenn der Inhalt für Sie von niedrigem Wert und die Leistungssteigerung erheblich ist, z.&#160;B. wenn große Binärdateien gesendet werden, die keinerlei Sicherheitsauswirkungen haben.  
  
### <a name="to-disable-digital-signing"></a>So deaktivieren Sie das digitale Signieren  
  
1. Erstellen Sie eine <xref:System.ServiceModel.Channels.CustomBinding>. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2. Fügen Sie der Bindungsauflistung entweder ein <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> oder ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> hinzu.  
  
3. Legen Sie die <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> oder die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> fest.  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Bindungen finden Sie unter [Erstellen von User-Defined Bindungen](../extending/creating-user-defined-bindings.md). Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung für einen bestimmten Authentifizierungsmodus finden Sie unter Gewusst [wie: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Security.MessageProtectionOrder>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Erstellen benutzerdefinierter Bindungen](../extending/creating-user-defined-bindings.md)
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
