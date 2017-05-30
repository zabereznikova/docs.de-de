---
title: "Änderungen der Neuzuweisungen in .NET Framework 4.6 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6
- application compatibility
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 19ad80233a79a4fdef89550696c1c3d33e14b355
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-46"></a>Änderungen der Neuzuweisungen in .NET Framework 4.6
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] neu kompiliert wurden. Sofern nicht anderweitig angegeben, wirken sich diese Änderungen nicht auf Binärdateien aus, die eine niedrigere Version von .NET Framework als Ziel haben, jedoch unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführt werden.  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [ASP.NET](#ASP)  
  
-   [Netzwerk](#Net)  
  
-   [Windows Communications Foundation (WCF)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [XML](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>Kernspeicher  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>, <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> und taskbasierte asynchrone Vorgänge mit <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601>|Bei Apps für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und höhere Versionen werden <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> im <xref:System.Threading.ExecutionContext> eines Threads gespeichert, der durch asynchrone Vorgänge verläuft.|Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> werden in asynchronen Tasks widergespiegelt, die nacheinander gestartet werden. Weitere Informationen finden Sie unter [Entschärfung: Kultur und asynchrone Vorgänge](../../../docs/framework/migration-guide/mitigation-culture-and-asynchronous-operations.md).|Nebenversion|  
  
<a name="ASP"></a>   
## <a name="aspnet"></a>ASP.NET  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|-------------|------------|------------|-----------|  
|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> mit einem `tagKey`-Wert von <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>|In Übereinstimmung mit dem HTML-Standard rendert die <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>-Methode <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> jetzt als nicht schließendes Tag in einer HTML-Antwort.|Das BR-Tag erzeugt nun einen Zeilenumbruch. Zuvor hat es zwei Zeilenumbrüche erzeugt.<br /><br /> Apps, die vom `<BR>`-Tag abhängig sind, um zwei Zeilenumbrüche zu erzeugen, können das vorherige Verhalten wiederherstellen, indem der <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>-Methode mit dem <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>-Argument ein zusätzlicher Aufruf hinzugefügt wird.|Gering|  
  
<a name="Net"></a>   
## <a name="networking"></a>Netzwerk  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> und <xref:System.Net.Security.SslStream?displayProperty=fullName>|Angefangen bei den Apps, die auf .NET Framework 4.6 abzielen, dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=fullName> und <xref:System.Net.Security.SslStream?displayProperty=fullName> eines der drei folgenden Protokolle verwenden: Tls1.0, Tls1.1 oder Tls 1.2.<br /><br /> Apps, die auf eine vorherige Version von .NET Framework abzielen, sind davon nicht betroffen, selbst wenn sie unter .NET Framework 4.6 ausgeführt werden.|Diese Änderung wirkt sich auf jede App aus, die auf .NET Framework 4.6 abzielt und SSL zum Kommunizieren mit einem HTTP- oder Socketserver unter Verwendung eines der der folgenden Typen verwendet: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.  Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](../../../docs/framework/migration-guide/mitigation-tls-protocols.md).|Nebenversion|  
  
<a name="WCF"></a>   
## <a name="windows-communications-foundation-wcf"></a>Windows Communications Foundation (WCF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|In der Implementierung von <xref:System.IdentityModel.Policy.AuthorizationContext>, der durch den Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> mit einem `null``authorizationPolicies`-Argument zurückgegeben wird, wurde die entsprechende Implementierung in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] geändert.|In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor. Wenn das alte Verhalten erforderlich ist, finden Sie unter [Entschärfung: Standardmäßiger AuthorizationContext](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md) entsprechende Informationen.|Nebenversion|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|Beginnend mit den Apps für .NET Framework 4.6, konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>-Methode Symbole mit PNG-Bildern erfolgreich in <xref:System.Drawing.Bitmap>-Objekte.<br /><br /> In Apps für .NET Framework 4.5.2 und frühere Versionen löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>-Methode eine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus, wenn das <xref:System.Drawing.Icon>-Objekt PNG-Bilder aufweist.|Diese Änderung betrifft Apps, die für .NET Framework 4.6 neu kompiliert werden und eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException>-Ausnahme bereitstellen, die ausgelöst wird, wenn ein <xref:System.Drawing.Icon>-Objekt PNG-Bilder aufweist. Wenn dieses Verhalten nicht erwünscht ist, wird das vorherige Verhalten von einem Konfigurationsschalter wiederhergestellt. Weitere Informationen finden Sie unter [Entschärfung: PNG-Bilder in Symbolobjekten](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|Nebenversion|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>|In Apps für .NET Framework 4.6 und 4.6.1 gehen Änderungen an den <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>-Eigenschaften, die innerhalb eines <xref:System.Windows.Threading.Dispatcher>-Objekts vorgenommen werden, am Ende dieses Dispatchervorgangs verloren. Auf ähnliche Weise werden außerhalb des Dispatchervorgangs vorgenommene Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> möglicherweise nicht widergespiegelt, wenn der Vorgang ausgeführt wird.|Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> werden zwischen Rückrufen der WPF-Benutzeroberfläche und anderem Code in einer WPF-Anwendung möglicherweise nicht weitergeben. Weitere Informationen finden Sie unter [Entschärfung: Kultur und Verteilervorgänge in WPF-Apps](../../../docs/framework/migration-guide/mitigation-culture-and-dispatcher-operations-in-wpf-apps.md).|Nebenversion|  
|Layoutglättung bei hohen DPIs|Die Art und Weise, wie Ränder und die Grenzen und der Hintergrund darin geglättet werden, hat sich geändert.|Das Layout der WPF-Steuerelemente kann sich leicht ändern. Weitere Informationen finden Sie unter [Entschärfung: WPF-Layout](../../../docs/framework/migration-guide/mitigation-wpf-layout.md).|Nebenversion|  
  
<a name="XML"></a>   
## <a name="xml"></a>XML  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|XSD-Schemavalidierung|Ab .NET Framework 4.6 erkennt die XSD-Schemavalidierung Verstöße gegen die Unique-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.|Weitere Informationen finden Sie unter [Entschärfung: XML-Schemavalidierung](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md).|Gering|  
|<xref:System.Xml.XmlWriter>|Bei Apps, die auf .NET Framework 4.5.2 oder niedrigere Versionen abzielen, löst das Schreiben eines ungültigen Ersatzzeichenpaars mithilfe der Fallbackbehandlung nicht immer eine Ausnahme aus.<br /><br /> Bei Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielen, löst der Versuch, ein ungültiges Ersatzzeichenpaar zu schreiben, eine <xref:System.ArgumentException>-Ausnahme aus.|Apps, die zur Neuausrichtung auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] neu kompiliert werden und ungültige Ersatzzeichenpaare schreiben, lösen jetzt eine Ausnahme in Fällen aus, in denen dies zuvor nicht der Fall war.|Rand|
