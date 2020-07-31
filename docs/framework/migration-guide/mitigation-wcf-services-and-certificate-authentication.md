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
# <a name="mitigation-wcf-services-and-certificate-authentication"></a>Entschärfung: WCF-Dienste und Zertifikatauthentifizierung

.NET Framework 4.6 fügt der Standardliste des WCF-SSL-Protokolls TLS 1.1 und TLS 1.2 hinzu. Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet.

## <a name="impact"></a>Auswirkungen

TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht. Wenn ein Kunde ein SSL-Zertifikat verwendet, das MD5 als Hashalgorithmus einsetzt, kann der WCF-Client keine Verbindung mit dem WCF-Dienst herstellen. Weitere Informationen finden Sie unter [Entschärfung: WCF-Dienste und Zertifikatauthentifizierung](mitigation-wcf-services-and-certificate-authentication.md).

## <a name="mitigation"></a>Minderung

Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:

- Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird. Dies ist die empfohlene Lösung.

- Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls. Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.

  > [!CAUTION]
  > Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.

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
      </system.serviceModel>
  </configuration>
  ```

- Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) oder einer früheren Version des Protokolls im Quellcode.

  > [!CAUTION]
  > Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.

## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
