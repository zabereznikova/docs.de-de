---
title: 'Entschärfung: WCF-Dienste und Zertifikatauthentifizierung'
description: In diesem Artikel erfahren Sie, wie Sie Probleme mit der Zertifikatauthentifizierung reduzieren, die durch Änderungen an der Standardliste für WCF-SSL-Protokolle in .NET Framework 4.6 entstehen.
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: b6460e58bb32151003430d6573c4bcf1b514081b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475371"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="adfd8-103">Entschärfung: WCF-Dienste und Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="adfd8-103">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="adfd8-104">.NET Framework 4.6 fügt der Standardliste des WCF-SSL-Protokolls TLS 1.1 und TLS 1.2 hinzu.</span><span class="sxs-lookup"><span data-stu-id="adfd8-104">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="adfd8-105">Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="adfd8-105">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="adfd8-106">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="adfd8-106">Impact</span></span>

<span data-ttu-id="adfd8-107">TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht.</span><span class="sxs-lookup"><span data-stu-id="adfd8-107">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="adfd8-108">Wenn ein Kunde ein SSL-Zertifikat verwendet, das MD5 als Hashalgorithmus einsetzt, kann der WCF-Client keine Verbindung mit dem WCF-Dienst herstellen.</span><span class="sxs-lookup"><span data-stu-id="adfd8-108">As a result, if a customer uses an SSL certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="adfd8-109">Weitere Informationen finden Sie unter [Entschärfung: WCF-Dienste und Zertifikatauthentifizierung](mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="adfd8-109">For more information, see [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="adfd8-110">Minderung</span><span class="sxs-lookup"><span data-stu-id="adfd8-110">Mitigation</span></span>

<span data-ttu-id="adfd8-111">Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="adfd8-111">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="adfd8-112">Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="adfd8-112">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="adfd8-113">Dies ist die empfohlene Lösung.</span><span class="sxs-lookup"><span data-stu-id="adfd8-113">This is the recommended solution.</span></span>

- <span data-ttu-id="adfd8-114">Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="adfd8-114">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="adfd8-115">Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="adfd8-115">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="adfd8-116">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="adfd8-116">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="adfd8-117">In der folgenden Konfigurationsdatei wird so vorgegangen:</span><span class="sxs-lookup"><span data-stu-id="adfd8-117">The following configuration file does this:</span></span>

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
      </system.serviceModel>
  </configuration>
  ```

- <span data-ttu-id="adfd8-118">Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) oder einer früheren Version des Protokolls im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="adfd8-118">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="adfd8-119">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="adfd8-119">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="adfd8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adfd8-120">See also</span></span>

- [<span data-ttu-id="adfd8-121">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="adfd8-121">Application compatibility</span></span>](application-compatibility.md)
