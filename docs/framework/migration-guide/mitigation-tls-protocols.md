---
title: 'Entschärfung: TLS-Protokolle'
description: Hier erhalten Sie Informationen zu Auswirkungen und Fehlerbehebungen bei TLS-Protokolländerungen ab .NET Framework 4.6.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: bb5aab3361663d7b5401d7e68688265fbc65b36f
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475358"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="7b4e0-103">Entschärfung: TLS-Protokolle</span><span class="sxs-lookup"><span data-stu-id="7b4e0-103">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="7b4e0-104">Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType> eines der drei folgenden Protokolle verwenden: Tls1.0, Tls1.1 oder Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-104">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="7b4e0-105">Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-105">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="7b4e0-106">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="7b4e0-106">Impact</span></span>  
 <span data-ttu-id="7b4e0-107">Von dieser Änderung sind folgende Punkte betroffen:</span><span class="sxs-lookup"><span data-stu-id="7b4e0-107">This change affects:</span></span>  
  
- <span data-ttu-id="7b4e0-108">Jede App, die SSL für die Kommunikation zu einem HTTPS- oder Socketserver mithilfe eines der folgenden Typen verwendet: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-108">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
- <span data-ttu-id="7b4e0-109">Alle serverseitigen Apps, die nicht für die Unterstützung von Tls1.0, Tls1.1 oder Tls 1.2 aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-109">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="7b4e0-110">Minderung</span><span class="sxs-lookup"><span data-stu-id="7b4e0-110">Mitigation</span></span>  
 <span data-ttu-id="7b4e0-111">Die empfohlene Minderung besteht darin, die serverseitige App auf Tls1.0, Tls1.1 oder Tls 1.2 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-111">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="7b4e0-112">Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen:</span><span class="sxs-lookup"><span data-stu-id="7b4e0-112">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
- <span data-ttu-id="7b4e0-113">Programmgesteuert, durch die Verwendung eines Codeausschnitts wie dem Folgenden:</span><span class="sxs-lookup"><span data-stu-id="7b4e0-113">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="7b4e0-114">Da das <xref:System.Net.ServicePointManager>-Objekt nur einmal initialisiert wird, muss die Anwendung zunächst diese Kompatibilitätseinstellungen definieren.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-114">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
- <span data-ttu-id="7b4e0-115">Durch Hinzufügen der folgenden Zeile zum Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der app.config-Datei:</span><span class="sxs-lookup"><span data-stu-id="7b4e0-115">By adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="7b4e0-116">Beachten Sie jedoch, dass das Abwählen des Standardverhaltens nicht empfohlen wird, da die Anwendung dadurch unsichererer wird.</span><span class="sxs-lookup"><span data-stu-id="7b4e0-116">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b4e0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b4e0-117">See also</span></span>

- [<span data-ttu-id="7b4e0-118">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="7b4e0-118">Application compatibility</span></span>](application-compatibility.md)
