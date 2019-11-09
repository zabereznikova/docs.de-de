---
title: Identität
description: Architektur von Cloud Native .net-apps für Azure | Identity
ms.date: 09/23/2019
ms.openlocfilehash: 4cc7c04bf323d2589777df466321f6801f511b6f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840346"
---
# <a name="identity"></a>Identität

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die meisten Softwareanwendungen müssen über Kenntnisse über den Benutzer oder den Prozess verfügen, von dem Sie aufgerufen werden. Der Benutzer oder Prozess, der mit einer Anwendung interagiert, wird als Sicherheits Prinzipal bezeichnet, und der Prozess der Authentifizierung und autorialisierung dieser Prinzipale wird als Identitätsverwaltung oder einfach als *Identität*bezeichnet. Einfache Anwendungen können Ihre gesamte Identitätsverwaltung in der Anwendung beinhalten. dieser Ansatz ist jedoch nicht gut mit vielen Anwendungen und vielen Arten von Sicherheits Prinzipale skalierbar. Windows unterstützt die Verwendung von Active Directory, um eine zentralisierte Authentifizierung und Autorisierung zu ermöglichen.

<!-- (insert figure showing Windows AD auth model) -->

Diese Lösung ist zwar in Unternehmensnetzwerken effektiv, aber Sie ist nicht für die Verwendung durch Benutzer oder Anwendungen konzipiert, die sich außerhalb der AD-Domäne befinden. Dank der Zunahme Internet basierter Anwendungen und der Zunahme von Cloud-Native apps haben sich die Sicherheitsmodelle weiterentwickelt.

Im heutigen cloudbasierten Identitäts Modell wird von der Architektur ausgegangen, dass Sie verteilt wird. Apps können an einer beliebigen Stelle bereitgestellt werden, und die Kommunikation mit anderen apps ist möglich. Clients können von überall aus mit diesen apps kommunizieren, und Clients können aus einer beliebigen Kombination von Plattformen und Geräten bestehen. Cloud-Native Identitätslösungen nutzen offene Standards, um den sicheren Anwendungs Zugriff von Clients zu erreichen. Diese Clients reichen von Menschen auf PCs oder Smartphones bis hin zu anderen apps, die überall online gehostet werden, zu Set-Top-Boxes und IOT-Geräten, auf denen eine beliebige Softwareplattform weltweit ausgeführt wird.

Moderne cloudbasierte Identitätslösungen nutzen in der Regel Zugriffs Token, die von einem Sicherheitstokendienst/Server (STS) für einen Sicherheits Prinzipal ausgegeben werden, sobald Ihre Identität bestimmt wird. Das Zugriffs Token, in der Regel ein JSON Web Token (JWT), umfasst *Ansprüche* zum Sicherheits Prinzipal. Diese Ansprüche enthalten mindestens die Identität des Benutzers, können aber auch zusätzliche Ansprüche enthalten, die von Anwendungen verwendet werden können, um die Zugriffsebene zu bestimmen, die dem Prinzipal erteilt wird.

<!-- (insert figure showing basic handshake involving a principal, an STS, and an app) -->

Der STS ist in der Regel nur für die Authentifizierung des Prinzipals verantwortlich. Die Bestimmung des Zugriffs Niveaus auf Ressourcen wird anderen Teilen der Anwendung überlassen.

## <a name="references"></a>Verweise

- [Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Zurück](azure-monitor.md)
>[Weiter](authentication-authorization.md)
