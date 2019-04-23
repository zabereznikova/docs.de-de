---
title: Erstellen eines signierten und/oder verschlüsselten benutzerdefinierten Headers
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: 76bfb6040f6b78765ed42ce7fbf86cdbd62c1e48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075629"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a><span data-ttu-id="d82cd-102">Erstellen eines signierten und/oder verschlüsselten benutzerdefinierten Headers</span><span class="sxs-lookup"><span data-stu-id="d82cd-102">Creating a custom header that is signed and-or encrypted</span></span>
<span data-ttu-id="d82cd-103">Beim Aufrufen eines Nicht-WCF-Dienstes mit einem WCF-Client müssen in einigen Fällen benutzerdefinierte SOAP-Header verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d82cd-103">When calling a non-WCF service using a WCF client it is sometimes necessary to use custom SOAP headers.</span></span> <span data-ttu-id="d82cd-104">In WCF ist ein Kanonisierungsfehler vorhanden, der verhindert, dass signierte und verschlüsselte benutzerdefinierte Header mit einem Nicht-WCF-Dienst verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d82cd-104">There is a canonicalization bug in WCF that prevents custom headers that are signed and encrypted from working with a non-WCF service.</span></span> <span data-ttu-id="d82cd-105">Dieses Problem wird durch die inkorrekte Kanonisierung von XML-Standardnamespaces verursacht.</span><span class="sxs-lookup"><span data-stu-id="d82cd-105">The problem is caused by the incorrect canonicalization of default XML namespaces.</span></span> <span data-ttu-id="d82cd-106">Es ist jedoch nur problematisch, wenn Nicht-WCF-Dienste mit benutzerdefinierten Headern aufgerufen werden, die signiert und/oder verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="d82cd-106">This is only problematic when calling non-WCF services with custom headers that are signed and/or encrypted.</span></span>  <span data-ttu-id="d82cd-107">Wenn der Dienst die Nachricht mit dem signierten und/oder verschlüsselten benutzerdefinierten Header empfängt, kann er die Signatur nicht verifizieren.</span><span class="sxs-lookup"><span data-stu-id="d82cd-107">When the service receives the message containing the signed and/or encrypted custom header it is unable to verify the signature.</span></span> <span data-ttu-id="d82cd-108">Mit der folgenden Problemumgehung wird der Kanonisierungsfehler vermieden, und die Interoperabilität mit Nicht-WCF-Diensten wird ermöglicht. Die Interoperabilität mit WCF-Diensten wird dabei jedoch nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="d82cd-108">This workaround avoids the canonicalization bug, allows interoperability with non-WCF services, but does not prevent interoperability with WCF services.</span></span>  
  
## <a name="defining-the-custom-header"></a><span data-ttu-id="d82cd-109">Definieren des benutzerdefinierten Headers</span><span class="sxs-lookup"><span data-stu-id="d82cd-109">Defining the custom header</span></span>  
 <span data-ttu-id="d82cd-110">Benutzerdefinierte Header werden definiert, indem ein Nachrichtenvertrag festgelegt wird und die als Header zu sendenden Member mit einem <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut markiert werden.</span><span class="sxs-lookup"><span data-stu-id="d82cd-110">Custom headers are defined by defining a message contract and marking the members you want to be sent as headers with a <xref:System.ServiceModel.MessageHeaderAttribute> attribute.</span></span> <span data-ttu-id="d82cd-111">Zur Umgehung des Kanonisierungsfehlers müssen Sie sicherstellen, dass das XML-Serialisierungsprogramm den Namespace für den benutzerdefinierten Header mit einem Präfix deklariert und nicht die Standardnamespacedeklaration verwendet.</span><span class="sxs-lookup"><span data-stu-id="d82cd-111">To work around the canonicalization bug you must ensure that the XML serializer declares the namespace for the custom header with a prefix instead of a default namespace declaration.</span></span> <span data-ttu-id="d82cd-112">Im folgenden Code wird veranschaulicht, wie der Datentyp für den Nachrichtenheader mit einer korrekten Namespacedeklaration definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d82cd-112">The following code shows how to define the data type that will be used as a message header with the correct namespace declaration.</span></span>  
  
```  
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
  
 <span data-ttu-id="d82cd-113">In diesem Code wird der neue Typ `msgHeaderElement` deklariert, der mit dem XML-Serialisierungsprogramm serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d82cd-113">This code declares a new type called `msgHeaderElement` that will be serialized with the XML Serializer.</span></span> <span data-ttu-id="d82cd-114">Beim Serialisieren einer Instanz dieses Typs wird ein Namespace mit dem Präfix 'h' definiert, wodurch der Kanonisierungsfehler umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="d82cd-114">When an instance of this type is serialized, it will define a namespace with an ‘h’ prefix, thus working around the canonicalization bug.</span></span>  <span data-ttu-id="d82cd-115">Im Nachrichtenvertrag wird dann eine Instanz von `msgHeaderElement` definiert, die mit dem <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut markiert wird, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d82cd-115">The message contract would then define an instance of `msgHeaderElement` and mark it with the <xref:System.ServiceModel.MessageHeaderAttribute> attribute as shown in the following example.</span></span>  
  
```  
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d82cd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d82cd-116">See also</span></span>

- [<span data-ttu-id="d82cd-117">Standardnachrichtenvertrag</span><span class="sxs-lookup"><span data-stu-id="d82cd-117">Default Message Contract</span></span>](../../../../docs/framework/wcf/samples/default-message-contract.md)
- [<span data-ttu-id="d82cd-118">Nachrichtenverträge</span><span class="sxs-lookup"><span data-stu-id="d82cd-118">Message Contracts</span></span>](../../../../docs/framework/wcf/samples/message-contracts.md)
- [<span data-ttu-id="d82cd-119">Verwenden von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="d82cd-119">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
