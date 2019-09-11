---
title: Erstellen eines signierten und/oder verschlüsselten benutzerdefinierten Headers
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: d737647f8c0442a3d6fa0d077a1ffe2c251ea043
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856175"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a>Erstellen eines signierten und/oder verschlüsselten benutzerdefinierten Headers
Beim Aufrufen eines Nicht-WCF-Dienstes mit einem WCF-Client müssen in einigen Fällen benutzerdefinierte SOAP-Header verwendet werden. In WCF ist ein Kanonisierungsfehler vorhanden, der verhindert, dass signierte und verschlüsselte benutzerdefinierte Header mit einem Nicht-WCF-Dienst verwendet werden können. Dieses Problem wird durch die inkorrekte Kanonisierung von XML-Standardnamespaces verursacht. Es ist jedoch nur problematisch, wenn Nicht-WCF-Dienste mit benutzerdefinierten Headern aufgerufen werden, die signiert und/oder verschlüsselt sind.  Wenn der Dienst die Nachricht mit dem signierten und/oder verschlüsselten benutzerdefinierten Header empfängt, kann er die Signatur nicht verifizieren. Mit der folgenden Problemumgehung wird der Kanonisierungsfehler vermieden, und die Interoperabilität mit Nicht-WCF-Diensten wird ermöglicht. Die Interoperabilität mit WCF-Diensten wird dabei jedoch nicht beeinträchtigt.  
  
## <a name="defining-the-custom-header"></a>Definieren des benutzerdefinierten Headers  
 Benutzerdefinierte Header werden definiert, indem ein Nachrichtenvertrag festgelegt wird und die als Header zu sendenden Member mit einem <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut markiert werden. Zur Umgehung des Kanonisierungsfehlers müssen Sie sicherstellen, dass das XML-Serialisierungsprogramm den Namespace für den benutzerdefinierten Header mit einem Präfix deklariert und nicht die Standardnamespacedeklaration verwendet. Im folgenden Code wird veranschaulicht, wie der Datentyp für den Nachrichtenheader mit einer korrekten Namespacedeklaration definiert wird.  
  
```csharp
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 In diesem Code wird der neue Typ `msgHeaderElement` deklariert, der mit dem XML-Serialisierungsprogramm serialisiert wird. Beim Serialisieren einer Instanz dieses Typs wird ein Namespace mit dem Präfix 'h' definiert, wodurch der Kanonisierungsfehler umgangen wird.  Im Nachrichtenvertrag wird dann eine Instanz von `msgHeaderElement` definiert, die mit dem <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut markiert wird, wie im folgenden Beispiel veranschaulicht.  
  
```csharp
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Standardnachrichtenvertrag](../../../../docs/framework/wcf/samples/default-message-contract.md)
- [Nachrichtenverträge](../../../../docs/framework/wcf/samples/message-contracts.md)
- [Verwenden von Nachrichtenverträgen](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
