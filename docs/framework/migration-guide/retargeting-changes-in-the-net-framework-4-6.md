---
title: "&#196;nderungen der Neuzuweisungen in .NET Framework 4.6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &#196;nderungen der Neuzuweisungen in .NET Framework 4.6
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] neu kompiliert wurden. Sofern nicht anderweitig angegeben, wirken sich diese Änderungen nicht auf Binärdateien aus, die eine niedrigere Version von .NET Framework als Ziel haben, jedoch unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführt werden.  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [ASP.NET](#ASP)  
  
-   [Netzwerk](#Net)  
  
-   [Windows Communications Foundation \(WCF\)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [XML](#XML)  
  
<a name="ASP"></a>   
## ASP.NET  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> mit einem `tagKey`\-Wert von <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>.|In Übereinstimmung mit dem HTML\-Standard rendert die <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>\-Methode jetzt <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> als nicht schließendes Tag in einer HTML\-Antwort.|Das BR\-Tag erzeugt nun einen Zeilenumbruch. Zuvor hat es zwei Zeilenumbrüche erzeugt.<br /><br /> Apps, die vom `<BR>`\-Tag abhängig sind, um zwei Zeilenumbrüche zu erzeugen, können das vorherige Verhalten wiederherstellen, indem der <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>\-Methode mit dem <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>\-Argument ein zusätzlicher Aufruf hinzugefügt wird.|Gering|  
  
<a name="Net"></a>   
## Netzwerk  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> und <xref:System.Net.Security.SslStream?displayProperty=fullName>|Angefangen bei den Apps, die auf .NET Framework 4.6 abzielen, dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=fullName> und <xref:System.Net.Security.SslStream?displayProperty=fullName> eines der drei folgenden Protokolle verwenden: Tls1.0, Tls1.1 oder Tls 1.2.<br /><br /> Apps, die auf eine vorherige Version von .NET Framework abzielen, sind davon nicht betroffen, selbst wenn sie unter .NET Framework 4.6 ausgeführt werden.|Diese Änderung wirkt sich auf jede App aus, die auf .NET Framework 4.6 abzielt und SSL zum Kommunizieren mit einem HTTP\- oder Socketserver unter Verwendung eines der der folgenden Typen verwendet: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.  Weitere Informationen finden Sie unter [Minderung: TLS\-Protokolle](../../../docs/framework/migration-guide/mitigation-tls-protocols.md).|Gering|  
  
<a name="WCF"></a>   
## Windows Communications Foundation \(WCF\)  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|Die Implementierung von <xref:System.IdentityModel.Policy.AuthorizationContext>, was durch den Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> mit einem Argument für `null``authorizationPolicies` zurückgegeben wird, hat die entsprechende Implementierung in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] geändert.|In seltenen Fällen liegen bei WCF\-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor. Wenn das alte Verhalten erforderlich ist, finden Sie weitere Informationen unter [Minderung: Standardmäßiger AuthorizationContext](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md).|Gering|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|Beginnend mit den Apps, die auf .NET Framework 4.6 ausgerichtet sind, konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>\-Methode Symbole mit PNG\-Bildern erfolgreich in <xref:System.Drawing.Bitmap>\-Objekte.<br /><br /> In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>\-Methode eine <xref:System.ArgumentOutOfRangeException>\-Ausnahme aus, wenn das <xref:System.Drawing.Icon>\-Objekt PNG\-Bilder aufweist.|Diese Änderung betrifft Apps, die neu kompiliert werden, um sie auf .NET Framework 4.6 auszurichten, und die eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException>\-Ausnahme bereitstellen, die ausgelöst wird, wenn ein <xref:System.Drawing.Icon>\-Objekt PNG\-Bilder aufweist. Wenn dieses Verhalten nicht erwünscht ist, wird das vorherige Verhalten von einem Konfigurationsschalter wiederhergestellt. Weitere Informationen finden Sie unter [Problemumgehung: PNG\-Bilder in Symbolobjekten](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|Gering|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|Layoutglättung bei hohen DPIs|Die Art und Weise, wie Ränder und die Grenzen und der Hintergrund darin geglättet werden, hat sich geändert.|Das Layout der WPF\-Steuerelemente kann sich leicht ändern. Weitere Informationen finden Sie unter [Minderung: WPF\-Layout](../../../docs/framework/migration-guide/mitigation-wpf-layout.md).|Gering|  
  
<a name="XML"></a>   
## XML  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|XSD\-Schemavalidierung|Ab .NET Framework 4.6 erkennt die XSD\-Schemavalidierung Verstöße gegen die Unique\-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.|Siehe [Minderung: XML\-Schema\-Validierung](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md).|Gering|  
|<xref:System.Xml.XmlWriter>|Bei Apps, die auf .NET Framework 4.5.2 oder niedrigere Versionen abzielen, löst das Schreiben eines ungültigen Ersatzzeichenpaars mithilfe der Fallbackbehandlung nicht immer eine Ausnahme aus.<br /><br /> Bei Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielen, löst der Versuch, ein ungültiges Ersatzzeichenpaar zu schreiben, eine <xref:System.ArgumentException>\-Ausnahme aus.|Apps, die zur Neuausrichtung auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] neu kompiliert werden und ungültige Ersatzzeichenpaare schreiben, lösen jetzt eine Ausnahme in Fällen aus, in denen dies zuvor nicht der Fall war.|Rand|