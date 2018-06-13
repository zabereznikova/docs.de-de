---
title: 'Vorgehensweise: Deaktivieren der Verschlüsselung digitaler Signaturen'
ms.date: 03/30/2017
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
ms.openlocfilehash: 074a32f6a69f8353568e76c99f4b65aece813f55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491659"
---
# <a name="how-to-disable-encryption-of-digital-signatures"></a>Vorgehensweise: Deaktivieren der Verschlüsselung digitaler Signaturen
Standardmäßig wird eine Nachricht signiert und die Signatur anschließend digital verschlüsselt. Dies wird gesteuert, indem eine benutzerdefinierte Bindung mit einer Instanz von <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> erstellt und anschließend die `MessageProtectionOrder`-Eigenschaft der jeweiligen Klasse auf einen <xref:System.ServiceModel.Security.MessageProtectionOrder>-Enumerationswert festgelegt wird. Die Standardeinstellung ist <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Dieser Prozess nimmt bis zu 30Prozent mehr Zeit in Anspruch als das einfache Signieren und Verschlüsseln auf Basis der Gesamtnachrichtengröße (je kleiner die Nachricht, desto geringer die Leistungsbeeinträchtigung). Wenn Sie die Verschlüsselung der Signatur jedoch deaktivieren, kann ein Angreifer eventuell den Inhalt der Nachricht ermitteln. Dies ist möglich, da das Signaturelement den Hashcode des reinen Texts des signierten Teils der Nachricht enthält. Obwohl zwar der Nachrichtentext standardmäßig verschlüsselt ist, enthält die unverschlüsselte Signatur beispielsweise den Hashcode des Nachrichtentexts vor der Verschlüsselung. Ist für den signierten und verschlüsselten Teil nur eine geringe Anzahl von Werten möglich, kann der Inhalt von einem Angreifer möglicherweise durch einen Blick auf den Hashwert ermittelt werden. Durch Verschlüsseln der Signatur ist diese Angriffsmöglichkeit nicht mehr gegeben.  
  
 Deaktivieren Sie aus diesem Grund die Verschlüsselung der Signatur nur dann, wenn der Wert des Inhalts gering, die Anzahl möglicher Inhaltswerte groß und nicht deterministisch ist und der Leistungsgewinn Vorrang vor der Vermeidung des oben beschriebenen Angriffsrisikos hat.  
  
> [!NOTE]
>  Enthält die Nachricht keinerlei verschlüsselte Inhalte, wird das Signaturelement nicht verschlüsselt. Dies gilt auch, wenn <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> oder die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> festgelegt ist. Dieses Verhalten tritt auch bei vom System bereitgestellten Bindungen auf. Für vom System bereitgestellte Bindungen ist die Nachrichtenschutzreihenfolge auf `SignBeforeEncryptAndEncryptSignature` festgelegt. Web Services Description Language (WSDL) WCF generiert wird jedoch weiterhin enthalten die `<sp:EncryptSignature>` Assertion.  
  
### <a name="to-disable-digital-signing"></a>So deaktivieren Sie das digitale Signieren  
  
1.  Erstellen Sie eine <xref:System.ServiceModel.Channels.CustomBinding>. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2.  Fügen Sie der Bindungsauflistung entweder ein <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> oder ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> hinzu.  
  
3.  Legen Sie die <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> oder die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> fest.  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
