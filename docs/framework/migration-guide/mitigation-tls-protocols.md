---
title: "Entschärfung: TLS-Protokolle | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1474aeb0e1be38018f9d27c49e8711800ecb9f01
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-tls-protocols"></a>Entschärfung: TLS-Protokolle
Von .NET Framework 4.6 an dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=fullName> und <xref:System.Net.Security.SslStream?displayProperty=fullName> eines der folgenden drei Protokolle verwenden: Tls1.0, Tls1.1 oder Tls 1.2. Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.  
  
## <a name="impact"></a>Auswirkungen  
 Von dieser Änderung sind folgende Punkte betroffen:  
  
-   Alle Apps, die SSL dazu verwenden, um mit einem HTTPS-Server oder einem Socketserver mithilfe eines der folgenden Typen zu kommunizieren: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.  
  
-   Alle serverseitigen Apps, die nicht für die Unterstützung von Tls1.0, Tls1.1 oder Tls 1.2 aktualisiert werden können.  
  
## <a name="mitigation"></a>Problemumgehung  
 Die empfohlene Entschärfung besteht darin, die serverseitige App auf Tls1.0, Tls1.1 oder Tls 1.2 zu aktualisieren. Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext> verwendet werden, um die Funktion auf zwei verschiedene Art und Weisen abzuwählen:  
  
-   Programmgesteuert, durch die Verwendung eines Codeausschnitts wie dem Folgenden:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Da das <xref:System.Net.ServicePointManager>-Objekt nur einmal initialisiert wird, muss die Anwendung zunächst diese Kompatibilitätseinstellungen definieren.  
  
-   Durch Hinzufügen der folgenden Zeile zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Datei „app.config“:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Beachten Sie jedoch, dass das Abwählen des Standardverhaltens nicht empfohlen wird, da die Anwendung dadurch unsichererer wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
