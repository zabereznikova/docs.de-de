---
title: "Entschärfung: WCF-Dienste und Zertifikatauthentifizierung | Microsoft-Dokumentation"
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
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f3dc4235c75d7438f019838cb22192f4dc7c41a
ms.openlocfilehash: 0b32fa96cd002e927fa00e8c2a797d1ff6b17cb8
ms.contentlocale: de-de
ms.lasthandoff: 05/30/2017

---
<a id="mitigation-wcf-services-and-certificate-authentication" class="xliff"></a>

# Entschärfung: WCF-Dienste und Zertifikatauthentifizierung
.NET Framework 4.6 fügt der Standardliste des WCF-SSL-Protokolls TLS 1.1 und TLS 1.2 hinzu. Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet.  
  
<a id="impact" class="xliff"></a>

## Auswirkungen  
 TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht. Wenn ein Kunde ein SSL-Zertifikat verwendet, das MD5 als Hashalgorithmus einsetzt, kann der WCF-Client daher keine Verbindung mit dem WCF-Dienst herstellen. Weitere Informationen finden Sie unter [Entschärfung: WCF-Dienste und Zertifikatauthentifizierung](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).  
  
<a id="mitigation" class="xliff"></a>

## Problemumgehung  
 Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:  
  
-   Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird. Dies ist die empfohlene Lösung.  
  
-   Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls. Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.  
  
    > [!CAUTION]
    >  Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.  
  
     In der folgenden Konfigurationsdatei wird so vorgegangen:  
  
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
  
-   Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=fullName>) oder einer früheren Version des Protokolls im Quellcode.  
  
    > [!CAUTION]
    >  Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.  
  
<a id="see-also" class="xliff"></a>

## Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

