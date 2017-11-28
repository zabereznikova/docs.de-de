---
title: "Entschärfung: WCF-Dienste und Zertifikatauthentifizierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bb852719e3312b78b86621e3cb69fa8bf7267856
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="b7044-102">Entschärfung: WCF-Dienste und Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="b7044-102">Mitigation: WCF Services and Certificate Authentication</span></span>
<span data-ttu-id="b7044-103">.NET Framework 4.6 fügt der Standardliste des WCF-SSL-Protokolls TLS 1.1 und TLS 1.2 hinzu.</span><span class="sxs-lookup"><span data-stu-id="b7044-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="b7044-104">Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7044-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="b7044-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="b7044-105">Impact</span></span>  
 <span data-ttu-id="b7044-106">TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht.</span><span class="sxs-lookup"><span data-stu-id="b7044-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="b7044-107">Wenn ein Kunde ein SSL-Zertifikat verwendet, das MD5 als Hashalgorithmus einsetzt, kann der WCF-Client daher keine Verbindung mit dem WCF-Dienst herstellen.</span><span class="sxs-lookup"><span data-stu-id="b7044-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="b7044-108">Weitere Informationen finden Sie unter [Entschärfung: WCF-Dienste und Zertifikatauthentifizierung](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b7044-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="b7044-109">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="b7044-109">Mitigation</span></span>  
 <span data-ttu-id="b7044-110">Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b7044-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>  
  
-   <span data-ttu-id="b7044-111">Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7044-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="b7044-112">Dies ist die empfohlene Lösung.</span><span class="sxs-lookup"><span data-stu-id="b7044-112">This is the recommended solution.</span></span>  
  
-   <span data-ttu-id="b7044-113">Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="b7044-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="b7044-114">Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7044-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="b7044-115">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="b7044-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
     <span data-ttu-id="b7044-116">In der folgenden Konfigurationsdatei wird so vorgegangen:</span><span class="sxs-lookup"><span data-stu-id="b7044-116">The following configuration file does this:</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="b7044-117">Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) oder einer früheren Version des Protokolls im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="b7044-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="b7044-118">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="b7044-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7044-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7044-119">See Also</span></span>  
 [<span data-ttu-id="b7044-120">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b7044-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
