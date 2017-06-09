---
title: "Key Security Concepts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "unauthorized access"
  - "permissions [.NET Framework]"
  - "security [.NET Framework], about security"
ms.assetid: 3cfced4f-ea02-4e66-ae98-d69286363e98
caps.latest.revision: 22
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 20
---
# Key Security Concepts
Microsoft .NET Framework bietet Sicherheitstransparenz, Codezugriffssicherheit und rollenbasierte Sicherheit, um Sicherheitsprobleme bei mobilem Code zu beheben und Komponenten die Möglichkeit einzuräumen, die Berechtigungen von Benutzern zu überprüfen.  Diese Sicherheitsmechanismen beruhen auf einem einfachen, konsistenten Modell. Entwickler, die mit Codezugriffssicherheit vertraut sind, haben daher keine Probleme im Umgang mit rollenbasierter Sicherheit und umgekehrt.  Codezugriffssicherheit und rollenbasierte Sicherheit werden mit einer gemeinsamen Infrastruktur implementiert, die von der Common Language Runtime bereitgestellt wird.  
  
> [!NOTE]
>  Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] bildet die Sicherheitstransparenz den standardmäßigen Erzwingungsmechanismus.  Durch Sicherheitstransparenz wird Code getrennt, der als Teil der Anwendung von Code ausgeführt wird, der wiederum als Teil der Infrastruktur ausgeführt wird.  Weitere Informationen finden Sie unter [Security\-Transparent Code](../../../docs/framework/misc/security-transparent-code.md).  
  
 Da Codezugriffssicherheit und rollenbasierte Sicherheit auf demselben Modell und derselben Infrastruktur beruhen, gelten für beide einige grundlegende Konzepte, die in diesem Abschnitt beschrieben werden.  Bevor Sie die Dokumentation zur Codezugriffssicherheit und rollenbasierten Sicherheit von .NET Framework lesen, sollten Sie sich unbedingt mit diesen Konzepten vertraut machen.  
  
## Sicherheitsberechtigungen  
 Die Common Language Runtime lässt für Code nur die Ausführung der Operationen zu, für die der Code über Berechtigungen verfügt.  Die Laufzeit verwendet als Berechtigungen bezeichnete Objekte, um Einschränkungen für verwalteten Code zu erzwingen.  Die Laufzeit stellt integrierte Berechtigungsklassen in verschiedenen Namespaces bereit und unterstützt darüber hinaus Entwurf und Implementierung benutzerdefinierter Berechtigungsklassen.  
  
 Es gibt zwei Arten von Berechtigungen, die jeweils einen bestimmten Zweck erfüllen:  
  
-   Codezugriffsberechtigungen stellen den Zugriff auf eine geschützte Ressource oder die Fähigkeit zum Ausführen einer geschützten Operation dar.  
  
-   Rollenbasierte Sicherheitsberechtigungen bieten die Möglichkeit aufzudecken, ob ein Benutzer \(oder der Agent, der im Auftrag des Benutzers agiert\) eine bestimmte Identität besitzt oder Member einer bestimmten Rolle ist.  <xref:System.Security.Permissions.PrincipalPermission> ist die einzige Berechtigung der rollenbasierten Sicherheit.  
  
 Sicherheitsberechtigungen können in Form einer Berechtigungsklasse \(imperative Sicherheit\) oder eines Attributs vorliegen, das eine Berechtigungsklasse darstellt \(deklarative Sicherheit\).  Die Basisklasse für Sicherheitsberechtigungen ist <xref:System.Security.CodeAccessPermission?displayProperty=fullName>, und die Basisklasse für Sicherheitsberechtigungsattribute ist <xref:System.Security.Permissions.CodeAccessSecurityAttribute?displayProperty=fullName>.  
  
 Einer Anwendung, die in Form einer Assembly vorhanden ist, wird beim Laden in eine Anwendungsdomäne ein Berechtigungssatz gewährt.  Die Berechtigungen werden in der Regel über vordefinierte Berechtigungssätze gewährt, die von der <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName>\-Methode festgelegt werden.  Der Berechtigungssatz bestimmt die Berechtigungen für den Code.  Die Laufzeit gewährt Berechtigungen anhand des ursprünglichen Speicherorts des Codes \(z. B. lokaler Computer, lokales Intranet oder Internet\).  Code können auch spezielle Berechtigungen erteilt werden, wenn er in einen Sandkasten geladen wird.  Weitere Informationen zum Ausführen von Code in einem Sandkasten finden Sie unter [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
 Berechtigungen werden hauptsächlich wie folgt eingesetzt:  
  
-   Bibliothekscode kann erfordern, dass der Aufrufer über bestimmte Berechtigungen verfügt.  Wenn Sie <xref:System.Security.CodeAccessPermission.Demand%2A> nach einer Berechtigung für Code festlegen, muss sämtlicher Code, der auf diesen Code zugreift, über die Berechtigung zur Ausführung verfügen.  Mithilfe von Demands kann festgestellt werden, ob Aufrufer Zugriff auf bestimmte Ressourcen haben oder die Identität eines Aufrufers ermitteln können.  
  
-   In Code können Ressourcen mithilfe von Berechtigungen vor Zugriff geschützt werden.  Mit <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> können Sie einen eingeschränkten Berechtigungssatz festlegen und alle anderen Berechtigungen implizit verweigern.  Es wird jedoch nicht empfohlen, mit <xref:System.Security.Permissions.SecurityAction> den Zugriff zu verhindern, um Ressourcen vor beabsichtigtem Missbrauch zu schützen.  Aufgerufene Assemblys, deren Berechtigungssatz die implizit verweigerten Berechtigungen enthält, können Berechtigungsverweigerungen überschreiben, indem sie für beliebige Berechtigungen, die sie verwenden möchten, <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> ausführen.  Wenn Sie z. B. nur <xref:System.Security.Permissions.UIPermission> zugelassen und eine Assembly aufgerufen haben, die inhärent über <xref:System.Security.Permissions.FileIOPermission> verfügt, kann die Assembly einfach für <xref:System.Security.Permissions.FileIOPermission> einen <xref:System.Security.Permissions.SecurityAction> und anschließend Dateioperationen ausführen.  Die einzige Möglichkeit, Ressourcen in Assemblys, auf die verwiesen wird, vor nicht vertrauenswürdigem Code zu schützen, besteht in der Ausführung von Code mit einem Berechtigungssatz, der diese Berechtigungen nicht enthält.  
  
### Codezugriffsberechtigungen  
 Codezugriffsberechtigungen sind Berechtigungsobjekte, mit denen Ressourcen und Operationen vor unbefugtem Zugriff geschützt werden.  Sie sind grundlegender Bestandteil der Verfahren, mit denen die Common Language Runtime Sicherheitsbeschränkungen für verwalteten Code erzwingt.  
  
 Jede Codezugriffsberechtigung entspricht einem der folgenden Rechte:  
  
-   Das Zugriffsrecht auf eine geschützte Ressource, z. B. Dateien oder Umgebungsvariablen.  
  
-   Das Recht, eine geschützte Operation durchzuführen, z. B. den Zugriff auf verwalteten Code.  
  
 Alle Codezugriffsberechtigungen können durch Code angefordert bzw. gefordert und, sofern vorhanden, durch die Laufzeit erteilt werden.  
  
 Alle Codezugriffsberechtigungen werden von der <xref:System.Security.CodeAccessPermission>\-Klasse abgeleitet, d. h., alle Codezugriffsberechtigungen verfügen über gemeinsam verwendete Methoden, z. B. **Demand**, **Assert**, **Deny**, **PermitOnly**, **IsSubsetOf**, **Intersect** und **Union**.  
  
> [!IMPORTANT]
>  In .[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wurde die Laufzeitunterstützung für die Erzwingung von Anforderungen für die Berechtigungen <xref:System.Security.Permissions.SecurityAction>, <xref:System.Security.Permissions.SecurityAction>, <xref:System.Security.Permissions.SecurityAction> und <xref:System.Security.Permissions.SecurityAction> entfernt.  Diese Anforderungen sollten nicht in Code verwendet werden, der auf [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] oder höher basiert.  Weitere Informationen zu diesen und anderen Änderungen finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
### Berechtigungen der rollenbasierten Sicherheit  
 <xref:System.Security.Permissions.PrincipalPermission> ist eine Berechtigung der rollenbasierten Sicherheit, mit deren Hilfe festgestellt werden kann, ob ein Benutzer über die angegebene Identität verfügt oder zu einer bestimmten Rolle gehört.  **PrincipalPermission** ist die einzige Berechtigung der rollenbasierten Sicherheit, die von der .NET Framework\-Klassenbibliothek bereitgestellt wird.  
  
## Typsicherheit und Sicherheit  
 Typsicherer Code greift nur auf die Speicheradressen zu, für die er über die erforderliche Berechtigung verfügt.  \(Typsicherheit bezieht sich in diesem Zusammenhang auf die Typsicherheit für den Speicher, nicht zu verwechseln mit der allgemeinen Typsicherheit.\) Typsicherer Code kann z. B. keine Werte aus den privaten Feldern eines anderen Objekts lesen.  Der Zugriff auf Typen ist genau definiert und muss zulässig sein.  
  
 Während der JIT\-Kompilierung \(Just\-In\-Time\) werden die Metadaten und MSIL \(Microsoft Intermediate Language\) einer Methode, die in systemeigenen Code des Computers JIT\-kompiliert werden soll, in einem optionalen Prüfungsvorgang auf ihre Typsicherheit überprüft.  Dieser Vorgang wird übersprungen, wenn der Code über die Berechtigung zum Umgehen der Überprüfung verfügt.  Weitere Informationen zur Überprüfung finden Sie unter [Der verwaltete Ausführungsprozess](../../../docs/standard/managed-execution-process.md).  
  
 Obwohl die Überprüfung der Typsicherheit für das Ausführen von verwaltetem Code nicht zwingend erforderlich ist, spielt die Typsicherheit eine wesentliche Rolle bei der Isolation von Assemblys und der Gewährleistung von Sicherheit.  Wenn Code typsicher ist, kann die Common Language Runtime Assemblys vollständig voneinander isolieren.  Diese Isolation trägt dazu bei, dass Assemblys einander nicht beeinträchtigen, und erhöht gleichzeitig die Zuverlässigkeit von Anwendungen.  Typsichere Komponenten können ohne Sicherheitseinbußen in demselben Prozess ausgeführt werden, selbst wenn sie unterschiedliche Vertrauensebenen aufweisen.  Wenn Code nicht typsicher ist, können unerwünschte Nebeneffekte auftreten.  So kann die Common Language Runtime z. B. nicht verhindern, dass verwalteter Code systemeigenen \(d. h. nicht verwalteten\) Code aufruft und schädliche Vorgänge ausführt.  Bei typsicherem Code gewährleistet die Durchsetzung von Sicherheit durch die Laufzeit, dass dieser nur mit der entsprechenden Berechtigung auf systemeigenen Code zugreifen kann.  Zum Ausführen von nicht typsicherem Code muss die <xref:System.Security.Permissions.SecurityPermission> mit dem übergebenen Enumerationsmember <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A> erteilt werden.  
  
 Weitere Informationen finden Sie unter [NIB: Writing Verifiably Type\-Safe Code](http://msdn.microsoft.com/de-de/d18f10ef-3b48-4f47-8726-96714021547b).  
  
## Principal  
 Ein Prinzipal stellt die Identität und die Rolle eines Benutzers dar und handelt stellvertretend für den Benutzer.  Die rollenbasierte Sicherheit in .NET Framework unterstützt drei Arten von Prinzipals:  
  
-   Allgemeine Prinzipals stellen Benutzer und Rollen dar, die unabhängig von Benutzern und Rollen unter Windows vorhanden sind.  
  
-   Windows\-Prinzipals stellen Windows\-Benutzer und ihre Rollen bzw. ihre Windows\-Gruppen dar.  Ein Windows\-Prinzipal kann einen anderen Benutzer imitieren, d. h., der Prinzipal kann im Namen eines Benutzers auf eine Ressource zugreifen, wenn er die Identität dieses Benutzers darstellt.  
  
-   Benutzerdefinierte Prinzipals können von einer Anwendung je nach Bedarf beliebig definiert werden.  Sie können die grundlegenden Eigenschaften der Identität und der Rollen des Prinzipals erweitern.  
  
 Weitere Informationen finden Sie unter [Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md).  
  
## Authentifizierung  
 Bei der Authentifizierung wird die Identität eines Prinzipals anhand der Anmeldeinformationen des Benutzers abgerufen und überprüft. Anschließend wird die Gültigkeit dieser Anmeldeinformationen mithilfe einer autorisierten Stelle überprüft.  Die bei der Authentifizierung abgerufenen Informationen können vom Code direkt verwendet werden.  Sie können den aktuellen Benutzer auch mit der rollenbasierten Sicherheit von .NET Framework authentifizieren und festlegen, ob der Prinzipal auf Ihren Code zugreifen kann.  Beispiele zur Authentifizierung des Prinzipals für bestimmte Rollen finden Sie in den Überladungen der <xref:System.Security.Principal.WindowsPrincipal.IsInRole%2A?displayProperty=fullName>\-Methode.  Sie können z. B. mit der <xref:System.Security.Principal.WindowsPrincipal.IsInRole%28System.String%29?displayProperty=fullName>\-Überladung ermitteln, ob der aktuelle Benutzer Mitglied der Administratorgruppe ist.  
  
 Derzeit werden verschiedene Authentifizierungsverfahren eingesetzt, von denen viele mit der rollenbasierten Sicherheit in .NET Framework verwendet werden können.  Am häufigsten werden Standard\-, Digest\-, Passport\- und Betriebssystemverfahren \(z. B. NTLM oder Kerberos\) sowie anwendungsdefinierte Verfahren verwendet.  
  
### Beispiel  
 Im folgenden Beispiel muss der aktive Prinzipal ein Administrator sein.  Der `name`\-Parameter ist `null`, sodass die Anforderung von allen Benutzern übergeben werden kann, die Administratoren sind.  
  
> [!NOTE]
>  Unter Windows Vista werden die Berechtigungen eines Benutzers über die Benutzerkontensteuerung \(User Account Control, UAC\) bestimmt.  Als Mitglied der integrierten Administratorgruppe sind Ihnen zwei Zugriffstoken für die Laufzeit zugewiesen: ein Standardbenutzertoken und ein Administratorzugriffstoken.  Standardmäßig verwenden Sie die Standardbenutzerrolle.  Um Code ausführen zu können, der Administratorberechtigungen erfordert, müssen Sie zuerst Ihre Berechtigungen von Standardbenutzer auf Administrator erhöhen.  Dazu starten Sie eine Anwendung, indem Sie mit der rechten Maustaste auf das Anwendungssymbol klicken und angeben, dass Sie die Anwendung als Administrator ausführen möchten.  
  
 [!code-cpp[Classic PrincipalPermission Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CPP/source.cpp#1)]
 [!code-csharp[Classic PrincipalPermission Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CS/source.cs#1)]
 [!code-vb[Classic PrincipalPermission Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/VB/source.vb#1)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie die Identität des Prinzipals sowie der Rollen bestimmt wird, die für den Prinzipal verfügbar sind.  Eine Anwendungsmöglichkeit für dieses Beispiel könnte darin bestehen, zu überprüfen, ob die Rolle des aktuellen Benutzers für die Verwendung der Anwendung zulässig ist.  
  
 [!code-cpp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CPP/source.cpp#1)]
 [!code-csharp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CS/source.cs#1)]
 [!code-vb[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/VB/source.vb#1)]  
  
## Autorisierung  
 Bei der Autorisierung wird bestimmt, ob das Ausführen einer angeforderten Aktion durch einen Prinzipal zulässig ist.  Die Autorisierung findet nach der Authentifizierung statt. Sie bestimmt anhand der Informationen zur Identität und Rollen des Prinzipals, auf welche Ressourcen dieser zugreifen darf.  Autorisierung können Sie in .NET Framework mithilfe der rollenbasierten Sicherheit implementieren.  
  
## Sicherheitsaspekte für interne virtuelle Schlüsselwörter  
 Die Sicherheit der Anwendung sollte nie auf einem Member beruhen, der in C\# mit dem Modifizierer [internal](../Topic/internal%20\(C%23%20Reference\).md) [virtual](../Topic/virtual%20\(C%23%20Reference\).md) \([Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) [Overridable](../Topic/Overridable%20\(Visual%20Basic\).md) [Friend](../Topic/Friend%20\(Visual%20Basic\).md) in Visual Basic\) gekennzeichnet ist.  Obwohl mit diesen Modifizierern gekennzeichnete Member nur von anderen Membern in der gleichen Assembly überschrieben werden können, wird diese Regel nur von den Sprachen C\# und Visual Basic erzwungen.  Die Laufzeit erzwingt diese Regel nicht.  Es ist daher möglich, mit **internal virtual** in C\# und **Overloads Overridable Friend** in Visual Basic gekennzeichnete Member unter Verwendung der Microsoft Intermediate Language oder jeder anderen Sprache zu überschreiben, die diese Regel nicht erzwingt.  
  
## Siehe auch  
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)