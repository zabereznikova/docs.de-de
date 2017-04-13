---
title: "Minderung: TLS-Protokolle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Minderung: TLS-Protokolle
Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=fullName> und <xref:System.Net.Security.SslStream?displayProperty=fullName> eines der drei folgenden Protokolle verwenden: Tls1.0, Tls1.1 oder Tls 1.2.  Weder das SSL3.0\-Protokoll noch das RC4\-Verschlüsselungsverfahren werden unterstützt.  
  
## Auswirkungen  
 Von dieser Änderung sind folgende Punkte betroffen:  
  
-   Jede App, die SSL für die Kommunikation zu einem HTTPS\- oder Socketserver mithilfe eines der folgenden Typen verwendet: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.  
  
-   Alle serverseitigen Apps, die nicht für die Unterstützung von Tls1.0, Tls1.1 oder Tls 1.2 aktualisiert werden können.  
  
## Problemumgehung  
 Die empfohlene Minderung besteht darin, die serverseitige App auf Tls1.0, Tls1.1 oder Tls 1.2 zu aktualisieren.  Wenn dies nicht möglich ist oder die Client\-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen:  
  
-   Programmgesteuert, durch die Verwendung eines Codeausschnitts wie dem Folgenden:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Da das <xref:System.Net.ServicePointManager>\-Objekt nur einmal initialisiert wird, muss die Anwendung zunächst diese Kompatibilitätseinstellungen definieren.  
  
-   Durch das Hinzufügen der folgenden Zeile zum Abschnitt [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Datei „app.config“ geschieht Folgendes:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Beachten Sie jedoch, dass das Abwählen des Standardverhaltens nicht empfohlen wird, da die Anwendung dadurch unsichererer wird.  
  
## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)