---
title: "Laufzeitänderungen in .NET Framework 4.6.2 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 23bf3a87-6fa1-4b5e-b92c-a39867a06e7f
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: da809955776b5a5cd3776898ecc4c97db74ceb0e
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-462"></a>Laufzeitänderungen in .NET Framework 4.6.2
In seltenen Fällen können sich Laufzeitänderungen auf vorhandene Apps auswirken, die auf frühere Versionen von .NET Framework abzielen, jedoch in einer älteren .NET Framework-Laufzeit ausgeführt werden. Sie umfassen auch Unterschiede im Verhalten zwischen Anwendungen, die in verschiedenen .NET Framework-Laufzeitumgebungen ausgeführt werden. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] umfasst Änderungen in folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [ASP.NET](#ASP)

-   [Data](#Data)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [XML-Signierung und -Validierung](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>Kernspeicher  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName><br /><br /> <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory%2A?displayProperty=fullName>|Die Zeichenkategorien in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] basieren auf Unicode-Version 8.0. Die als Unicode klassifizierten Zeichen in .NET Framework, Version 4.5 bis 4.6.1, basieren auf Unicode-Version 6.3.<br /><br /> Zeichenvergleich und Sortierung sind von dieser Änderung nicht betroffen. Weitere Informationen finden sie im Abschnitt „Zeichenfolgen und Unicode-Standard“ im Thema zur <xref:System.String>-Klasse.|Zeichenkategorien in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] stimmen möglicherweise nicht mit denen früherer Versionen von .NET Framework überein. Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen und Tonmarkierungen.<br /><br /> Um dieser Änderung Rechnung zu tragen, sollten Sie Code überprüfen und Logik entfernen oder ändern, die von hartcodierten Unicode-Zeichenkategorien abhängt.|Gering|  
|<xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.RSACng.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=fullName>|Ab [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] können diese Methoden auf Schlüssel für RSA-Zertifikate mit nicht standardmäßigen Schlüssellängen zugreifen. In Version [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen lösen Zugriffsversuche auf diese Schlüssel eine <xref:System.Security.Cryptography.CryptographicException>-Ausnahme aus.|Wenn sich Code zur Ausnahmebehandlung auf eine <xref:System.Security.Cryptography.CryptographicException>-Ausnahme bei der Verwendung nicht standardmäßiger Schlüssellängen stützt, sollte er entfernt werden.|Kante|  
|<xref:System.Security.Cryptography.RSACng.VerifyHash%2A?displayProperty=fullName>|Ab [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] gibt diese Methode `false` zurück, wenn die Signatur selbst ein ungültiges Format aufweist. Jetzt wird für alle Überprüfungsfehler `false` zurückgegeben.<br /><br /> In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und 4.6.1 löst die Methode eine <xref:System.Security.Cryptography.CryptographicException>-Ausnahme aus, wenn die Signatur selbst ein ungültiges Format aufweist.|Jeder Code, dessen Ausführung von der <xref:System.Security.Cryptography.CryptographicException>-Ausnahme abhängt, sollte stattdessen ausgeführt werden, wenn ein Validierungsfehler auftritt und die Methode `false` zurückgibt.|Gering|  
  
## <a name="a-nameasp--aspnet"></a><a name="ASP" />ASP.NET

|Funktion|Änderung|Auswirkungen|Bereich| 
|-------------|------------|------------|-----------|  
| <xref:System.Web.HttpRuntime.AppDomainApopPath%2A> | In .NET Framework 4.6.2 löst die Runtime eine <xref:System.NullReferenceException>-Ausnahme aus, wenn ein <xref:System.Web.HttpRuntime.AppDomainAppPath%2A>-Wert abgerufen wird, der NULL-Zeichen enthält. In .NET Framework 4.6.1 und früheren Versionen wird eine <xref:System.ArgumentNullException>-Ausnahme ausgelöst.  | Sie können in der folgenden Weise auf diese Änderung reagieren: <br/> – Die <xref:System.NullReferenceException>-Ausnahme behandeln, wenn Ihre Anwendung in .NET Framework 4.6.2 ausgeführt wird. <br /> – Ein Upgrade auf .NET Framework 4.7 vornehmen, wodurch das vorherige Verhalten wiederhergestellt und eine <xref:System.ArgumentNullException>-Ausnahme ausgelöst wird. | Edge |

<a name="Data"></a>   
## <a name="data"></a>Daten  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Verbindungspool-Sperrfrist für Azure SQL-Datenbanken|Für Anforderungen zum Öffnen von Verbindungen mit bekannten Azure SQL-Datenbanken entfällt die Verbindungspool-Sperrfrist.|Wiederholungsversuche von Anforderungen zum Öffnen von Verbindungen erfolgen nahezu unmittelbar nach vorübergehenden Verbindungsfehlern. Weitere Informationen finden Sie unter [Problemumgehung: Poolsperrfrist](~/docs/framework/migration-guide/mitigation-pool-blocking-period.md).|Gering|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> <br /> <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>|Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird das SSL3-Protokoll nicht mehr als eins der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet.|In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 schon immer in der Protokollliste für NetTcp enthalten ist. Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln.<br /><br /> Wenn SSL3 erforderlich ist, können Sie einen der folgenden Konfigurationsmechanismen verwenden, um SSL3 zur Liste der ausgehandelten Protokolle hinzuzufügen:<br /><br /> – Die <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName>-Eigenschaft<br />– Die <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName>-Eigenschaft<br />– Der [\<transport>](~/docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)-Abschnitt von [\<netTcpBinding>](~/docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)<br />– Der [\<sslStreamSecurity>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)-Abschnitt von [\<customBinding>](~/docs/framework/configure-apps/file-schema/wcf/custombinding.md)|Edge|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Die `IsEnabled`-Eigenschaft des übergeordneten Elements eines <xref:System.Windows.Controls.TextBlock>-Steuerelements|Ab [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wirken sich Änderungen an der `IsEnabled`-Eigenschaft des übergeordneten Elements eines <xref:System.Windows.Controls.TextBlock>-Steuerelements auf alle untergeordneten Steuerelemente (wie etwa Links und Schaltflächen) des <xref:System.Windows.Controls.TextBlock>-Steuerelements aus.<br /><br /> In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen von .NET Framework gaben Steuerelemente innerhalb eines <xref:System.Windows.Controls.TextBlock>-Steuerelements nicht immer den Status der `IsEnabled`-Eigenschaft des übergeordneten <xref:System.Windows.Controls.TextBlock>-Elements wieder.|Diese Änderung entspricht dem erwarteten Verhalten für Steuerelemente innerhalb eines <xref:System.Windows.Controls.TextBlock>-Steuerelements.|Gering|  
|Horizontales Scrollen, Virtualisierung und <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>|Das Verhalten des Scrollvorgangs für ein <xref:System.Windows.Controls.ItemsControl>-Steuerelement mit eigener Virtualisierung in der Richtung senkrecht zur Hauptscrollrichtung hat sich geändert.|Die Änderung ergibt ein besser vorhersehbares und intuitiveres Verhalten für den Endbenutzer, sie kann sich aber auf jede App auswirken, die auf den genauen Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> nach einem horizontalen Scrollvorgang angewiesen ist. Weitere Informationen finden Sie unter [Problemumgehung: Horizontales Scrollen und Virtualisierung](~/docs/framework/migration-guide/mitigation-horizontal-scrolling-and-virtualization.md).|Gering|  
|WPF-Rechtschreibprüfung (<xref:System.Windows.Controls.SpellCheck?displayProperty=fullName>-Klasse)|Drei bei der WPF-Rechtschreibprüfung bemerkte Probleme bei der Ausführung in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] wurden in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] behandelt:<br /><br /> – In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] löst die Rechtschreibprüfung manchmal beim Aufrufen der Methode [ISpellChecker](https://msdn.microsoft.com/library/windows/desktop/hh869767\(v=vs.85\).aspx) oder [ISpellCheckerFactory](https://msdn.microsoft.com/library/windows/desktop/hh869770\(v=vs.85\).aspx) eine <xref:System.Runtime.InteropServices.COMException>-Ausnahme aus. In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurden diese Ausnahmen beseitigt.<br />– In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] erkennt die Rechtschreibprüfung fälschlicherweise Rechtschreibfehler in zusammengesetzten deutschen Wörtern, wie „Hausnummer“. In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] verarbeitet die Rechtschreibprüfung zusammengesetzte Wörter ordnungsgemäß.<br />– In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] löst die Rechtschreibprüfung eine <xref:System.UnauthorizedAccessException>-Ausnahme aus, wenn eine Anwendung mithilfe von „Als anderer Benutzer ausführen“ gestartet wird. In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wird dieses Szenario nicht unterstützt, und die Rechtschreibprüfung wird ohne Rückmeldung deaktiviert.|Diese Änderungen erhöhen die Stabilität der Rechtschreibprüfung.  Sie sollten sich nicht negativ auf Anwendungen auswirken, es sei denn, dass Anwendungscode vom Auslösen einer Ausnahme abhängt.|Edge|  
| [DataGridCellsPanel.BringIndexIntoView](xref:System.Windows.Controls.DataGridCellsPanel.BringIndexInfoView(System.Int32))-Methode | In .NET Framework 4.6.2 wird die **BringIndexIntoView**-Methode asynchron ausgeführt, wenn Spaltenvirtualisierung aktiviert ist, die Spaltenbreiten aber nicht festgelegt wurden. Wenn jedoch Spalten entfernt werden, bevor der asynchrone Vorgang abgeschlossen ist, kann eine [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException)-Ausnahme auftreten.<br/></br>Ab .NET Framework 4.7 wird die Ausnahme in diesem Szenario nicht mehr ausgelöst. | Sie können eine der folgenden Maßnahmen ergreifen, um das Auftreten der Ausnahme zu verhindern: <br/> – Ein Upgrade auf .NET Framework 4.7 vornehmen. <br/> Den neuesten Servicepatch für .NET Framework 4.6.2 installieren. <br/> – Das Entfernen von Spalten vermeiden, bis die asynchrone Antwort auf die [DataGrid.ScrollIntoView](xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object))-Methode abgeschlossen wurde. | Edge | 
  
<a name="XML"></a>   
## <a name="signed-xml-verification-requirements"></a>Anforderungen an die Überprüfung von signiertem XML  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> und <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName>|Das Laden von externen Ressourcen ist deaktiviert, und Ziele mit nicht eindeutiger ID werden als ungültig angesehen.|In einer Reihe von Fällen wird eine Ausnahme ausgelöst, darunter:<br /><br /> – Beim Identifizieren eines Elements anhand eines ID-Attributs, wenn ein zweites Element mit dem gleichen Bezeichner definiert wird,<br />– Beim Definieren eines Bezeichners, der keinen zulässigen `NCName`-Wert darstellt.<br />– Beim Verweis auf externe URIs.<br /><br /> <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A?displayProperty=fullName> gibt für diese Dokumente immer `false` zurück:<br /><br /> – die die Referenz zu XPath-Transformation verwenden.<br />– die die Referenz zu XSLT-Transformation verwenden.<br /><br /> Entwickler sollten die Verwendung von <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=fullName> und <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> sowie von Typen überprüfen, die von <xref:System.Security.Cryptography.Xml.Transform?displayProperty=fullName> abgeleitet sind, da der Empfänger eines Dokuments möglicherweise nicht imstande ist, es zu verarbeiten.<br /><br /> Weitere Informationen finden Sie unter [Nach der Installation von Sicherheitsupdate 3141780 können in .NET Framework-Anwendungen während der Verarbeitung von Dateien, die SignedXml enthalten, Ausnahmefehler oder unerwartete Fehler auftreten](https://support.microsoft.com/en-us/kb/3148821).|Gering|  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungskompatibilität in 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
