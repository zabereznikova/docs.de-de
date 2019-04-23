---
title: 'Entschärfung: TLS-Protokolle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70fab3dc418e3eb92e39a7c2b1365e8582b81834
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125093"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="1650a-102">Entschärfung: TLS-Protokolle</span><span class="sxs-lookup"><span data-stu-id="1650a-102">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="1650a-103">Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType> eines der folgenden drei Protokolle verwenden: TLS 1.0, TLS 1.1 oder TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1650a-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="1650a-104">Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1650a-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="1650a-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="1650a-105">Impact</span></span>  
 <span data-ttu-id="1650a-106">Von dieser Änderung sind folgende Punkte betroffen:</span><span class="sxs-lookup"><span data-stu-id="1650a-106">This change affects:</span></span>  
  
-   <span data-ttu-id="1650a-107">Jede App, die SSL für die Kommunikation zu einem HTTPS- oder Socketserver mithilfe eines der folgenden Typen verwendet: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.</span><span class="sxs-lookup"><span data-stu-id="1650a-107">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
-   <span data-ttu-id="1650a-108">Alle serverseitigen Apps, die nicht für die Unterstützung von Tls1.0, Tls1.1 oder Tls 1.2 aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1650a-108">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="1650a-109">Minderung</span><span class="sxs-lookup"><span data-stu-id="1650a-109">Mitigation</span></span>  
 <span data-ttu-id="1650a-110">Die empfohlene Minderung besteht darin, die serverseitige App auf Tls1.0, Tls1.1 oder Tls 1.2 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1650a-110">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="1650a-111">Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen: </span><span class="sxs-lookup"><span data-stu-id="1650a-111">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
-   <span data-ttu-id="1650a-112">Programmgesteuert, durch die Verwendung eines Codeausschnitts wie dem Folgenden:</span><span class="sxs-lookup"><span data-stu-id="1650a-112">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="1650a-113">Da das <xref:System.Net.ServicePointManager>-Objekt nur einmal initialisiert wird, muss die Anwendung zunächst diese Kompatibilitätseinstellungen definieren.</span><span class="sxs-lookup"><span data-stu-id="1650a-113">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
-   <span data-ttu-id="1650a-114">Durch Hinzufügen der folgenden Zeile zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Datei „app.config“:</span><span class="sxs-lookup"><span data-stu-id="1650a-114">By adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="1650a-115">Beachten Sie jedoch, dass das Abwählen des Standardverhaltens nicht empfohlen wird, da die Anwendung dadurch unsichererer wird.</span><span class="sxs-lookup"><span data-stu-id="1650a-115">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1650a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1650a-116">See also</span></span>

- [<span data-ttu-id="1650a-117">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="1650a-117">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
