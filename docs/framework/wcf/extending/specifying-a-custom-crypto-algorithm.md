---
title: Angeben eines benutzerdefinierten Kryptografiealgorithmus
ms.date: 03/30/2017
ms.assetid: d662a305-8e09-451d-9a59-b0f12b012f1d
ms.openlocfilehash: 673d177a665e265d77f0221e0a00f4b814c8795c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186487"
---
# <a name="specifying-a-custom-crypto-algorithm"></a><span data-ttu-id="9d830-102">Angeben eines benutzerdefinierten Kryptografiealgorithmus</span><span class="sxs-lookup"><span data-stu-id="9d830-102">Specifying a Custom Crypto Algorithm</span></span>
<span data-ttu-id="9d830-103">WCF ermöglicht es Ihnen, beim Verschlüsseln von Daten oder Berechnen digitaler Signaturen einen benutzerdefinierten Kryptografiealgorithmus anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9d830-103">WCF allows you to specify a custom crypto algorithm to use when encrypting data or computing digital signatures.</span></span> <span data-ttu-id="9d830-104">Dazu führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9d830-104">This is done by the following steps:</span></span>  
  
1. <span data-ttu-id="9d830-105">Leiten Sie eine Klasse von <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> ab.</span><span class="sxs-lookup"><span data-stu-id="9d830-105">Derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite></span></span>  
  
2. <span data-ttu-id="9d830-106">Registrieren Sie den Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="9d830-106">Register the algorithm</span></span>  
  
3. <span data-ttu-id="9d830-107">Konfigurieren Sie die Bindung mit der <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9d830-107">Configure the binding with the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class.</span></span>  
  
## <a name="derive-a-class-from-securityalgorithmsuite"></a><span data-ttu-id="9d830-108">Ableiten einer Klasse von SecurityAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9d830-108">Derive a class from SecurityAlgorithmSuite</span></span>  
 <span data-ttu-id="9d830-109"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite> ist eine abstrakte Basisklasse, mit der Sie den Algorithmus für verschiedene sicherheitsbezogene Vorgänge angeben können,</span><span class="sxs-lookup"><span data-stu-id="9d830-109">The <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> is an abstract base class that allows you to specify the algorithm to use when performing various security related operations.</span></span> <span data-ttu-id="9d830-110">z. B. für das Berechnen eines Hash für eine digitale Signatur oder das Verschlüsseln einer Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d830-110">For example, computing a hash for a digital signature or encrypting a message.</span></span> <span data-ttu-id="9d830-111">Der folgende Code zeigt, wie eine Klasse von <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> abgeleitet wird:</span><span class="sxs-lookup"><span data-stu-id="9d830-111">The following code shows how to derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span></span>  
  
```csharp  
public class MyCustomAlgorithmSuite : SecurityAlgorithmSuite  
    {  
        public override string DefaultAsymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaOaepKeyWrap; }  
        }  
  
        public override string DefaultAsymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaSha1Signature; }  
        }  
  
        public override string DefaultCanonicalizationAlgorithm  
        {  
            get { return SecurityAlgorithms.ExclusiveC14n; ; }  
        }  
  
        public override string DefaultDigestAlgorithm  
        {  
            get { return SecurityAlgorithms.MyCustomHashAlgorithm; }  
        }  
  
        public override string DefaultEncryptionAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override int DefaultEncryptionKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSignatureKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSymmetricKeyLength  
        {  
            get { return 128; }  
        }  
  
        public override string DefaultSymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override string DefaultSymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.HmacSha1Signature; }  
        }  
  
        public override bool IsAsymmetricKeyLengthSupported(int length)  
        {  
            return length >= 1024 && length <= 4096;  
        }  
  
        public override bool IsSymmetricKeyLengthSupported(int length)  
        {  
            return length >= 128 && length <= 256;  
        }  
    }  
```  
  
## <a name="register-the-custom-algorithm"></a><span data-ttu-id="9d830-112">Registrieren des benutzerdefinierten Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9d830-112">Register the Custom Algorithm</span></span>  
 <span data-ttu-id="9d830-113">Die Registrierung kann in einer Konfigurationsdatei oder in imperativem Code vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9d830-113">Registration can be done in a configuration file or in imperative code.</span></span> <span data-ttu-id="9d830-114">Zum Registrieren eines benutzerdefinierten Algorithmus wird eine Zuordnung zwischen einer Klasse, die einen Kryptografiedienstanbieter implementiert, und einem Alias erstellt.</span><span class="sxs-lookup"><span data-stu-id="9d830-114">Registering a custom algorithm is done by creating a mapping between a class that implements a crypto service provider and an alias.</span></span> <span data-ttu-id="9d830-115">Der Alias wird dann einem URI zugeordnet, der beim Angeben des Algorithmus in der Bindung des WCF-Diensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d830-115">The alias is then mapped to a URI which is used when specifying the algorithm in the WCF service’s binding.</span></span> <span data-ttu-id="9d830-116">Der folgende Konfigurationsausschnitt zeigt, wie ein benutzerdefinierter Algorithmus in der Konfigurationsdatei registriert wird:</span><span class="sxs-lookup"><span data-stu-id="9d830-116">The following configuration snippet illustrates how to register a custom algorithm in config:</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
           <cryptoClasses>  
              <cryptoClass SHA256CSP="System.Security.Cryptography.SHA256CryptoServiceProvider, System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
           </cryptoClasses>  
           <nameEntry name="http://constoso.com/CustomAlgorithms/CustomHashAlgorithm"  
              class="SHA256CSP" />  
           </cryptoNameMapping>  
        </cryptographySettings>  
    </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="9d830-117">Der Abschnitt unter `cryptoClasses` dem <>-Element erstellt die Zuordnung zwischen dem SHA256CryptoServiceProvider und dem Alias "SHA256CSP".</span><span class="sxs-lookup"><span data-stu-id="9d830-117">The section under the <`cryptoClasses`> element creates the mapping between the SHA256CryptoServiceProvider and the alias "SHA256CSP".</span></span> <span data-ttu-id="9d830-118">Das `nameEntry` <>-Element erstellt die Zuordnung zwischen dem Alias "SHA256CSP" und der angegebenen URL `http://constoso.com/CustomAlgorithms/CustomHashAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="9d830-118">The <`nameEntry`> element creates the mapping between the "SHA256CSP" alias and the specified URL `http://constoso.com/CustomAlgorithms/CustomHashAlgorithm`.</span></span>  
  
 <span data-ttu-id="9d830-119">Verwenden Sie zum Registrieren des benutzerdefinierten Algorithmus im Code die <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])>-Methode.</span><span class="sxs-lookup"><span data-stu-id="9d830-119">To register the custom algorithm in code use the <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> method.</span></span> <span data-ttu-id="9d830-120">Diese Methode erstellt beide Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="9d830-120">This method creates both mappings.</span></span> <span data-ttu-id="9d830-121">Das folgende Beispiel zeigt, wie diese Methode aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="9d830-121">The following example shows how to call this method:</span></span>  
  
```csharp
// Register the custom URI string defined for the hashAlgorithm in MyCustomAlgorithmSuite class to create the
// SHA256CryptoServiceProvider hash algorithm object.  
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), "http://constoso.com/CustomAlgorithms/CustomHashAlgorithm");  
```  
  
## <a name="configure-the-binding"></a><span data-ttu-id="9d830-122">Konfigurieren der Bindung</span><span class="sxs-lookup"><span data-stu-id="9d830-122">Configure the Binding</span></span>  
 <span data-ttu-id="9d830-123">Zum Konfigurieren der Bindung geben Sie die benutzerdefinierte abgeleitete <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse wie im folgenden Codeausschnitt dargestellt in den Bindungseinstellungen an:</span><span class="sxs-lookup"><span data-stu-id="9d830-123">You configure the binding by specifying the custom <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class in the binding settings as shown in the following code snippet:</span></span>  
  
```csharp  
WSHttpBinding binding = new WSHttpBinding();  
            binding.Security.Message.AlgorithmSuite = new MyCustomAlgorithmSuite();  
```  
  
 <span data-ttu-id="9d830-124">Ein vollständiges Codebeispiel finden Sie im Beispiel [Kryptografische Beweglichkeit in WCF-Sicherheit.](../samples/cryptographic-agility-in-wcf-security.md)</span><span class="sxs-lookup"><span data-stu-id="9d830-124">For a complete code example, see the [Cryptographic Agility in WCF Security](../samples/cryptographic-agility-in-wcf-security.md) sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d830-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d830-125">See also</span></span>

- [<span data-ttu-id="9d830-126">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="9d830-126">Securing Services and Clients</span></span>](../feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9d830-127">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="9d830-127">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="9d830-128">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="9d830-128">Security Overview</span></span>](../feature-details/security-overview.md)
- [<span data-ttu-id="9d830-129">Sicherheitskonzepte</span><span class="sxs-lookup"><span data-stu-id="9d830-129">Security Concepts</span></span>](../feature-details/security-concepts.md)
