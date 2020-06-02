---
title: Schlüsselbegriffe der Sicherheit
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- unauthorized access
- permissions [.NET Framework]
- security [.NET Framework], about security
ms.assetid: 3cfced4f-ea02-4e66-ae98-d69286363e98
ms.openlocfilehash: 1ec811430056b7db575d6db229a3afe618850e49
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291239"
---
# <a name="key-security-concepts"></a>Schlüsselbegriffe der Sicherheit
Microsoft .NET Framework bietet rollenbasierte Sicherheit, um Sicherheitsprobleme bei mobilem Code zu beheben und Komponenten die Möglichkeit einzuräumen, die Berechtigungen von Benutzern zu überprüfen.  
  
## <a name="type-safety-and-security"></a>Typsicherheit und Sicherheit  
 Typsicherer Code greift nur auf die Speicheradressen zu, für die er über die erforderliche Berechtigung verfügt. (Die Typsicherheit bezieht sich in diesem Zusammenhang speziell auf die Sicherheit des Speicher Typs und sollte in größerem Umfang nicht mit der Typsicherheit verwechselt werden.) Typsicherer Code kann z. b. keine Werte aus den privaten Feldern eines anderen Objekts lesen. Der Zugriff auf Typen ist genau definiert und muss zulässig sein.  
  
 Während der JIT-Kompilierung (Just-In-Time) werden die Metadaten und MSIL (Microsoft Intermediate Language) einer Methode, die in systemeigenen Code des Computers JIT-kompiliert werden soll, in einem optionalen Prüfungsvorgang auf ihre Typsicherheit überprüft. Dieser Vorgang wird übersprungen, wenn der Code über die Berechtigung zum Umgehen der Überprüfung verfügt. Weitere Informationen über Überprüfung finden Sie unter [Der verwaltete Ausführungsprozess](../managed-execution-process.md).  
  
 Obwohl die Überprüfung der Typsicherheit für das Ausführen von verwaltetem Code nicht zwingend erforderlich ist, spielt die Typsicherheit eine wesentliche Rolle bei der Isolation von Assemblys und der Gewährleistung von Sicherheit. Wenn Code typsicher ist, kann die Common Language Runtime Assemblys vollständig voneinander isolieren. Diese Isolation trägt dazu bei, dass Assemblys einander nicht beeinträchtigen, und erhöht gleichzeitig die Zuverlässigkeit von Anwendungen. Typsichere Komponenten können ohne Sicherheitseinbußen in demselben Prozess ausgeführt werden, selbst wenn sie unterschiedliche Vertrauensebenen aufweisen. Wenn Code nicht typsicher ist, können unerwünschte Nebeneffekte auftreten. So kann die Common Language Runtime z. B. nicht verhindern, dass verwalteter Code systemeigenen (d. h. nicht verwalteten) Code aufruft und schädliche Vorgänge ausführt. Bei typsicherem Code gewährleistet die Durchsetzung von Sicherheit durch die Laufzeit, dass dieser nur mit der entsprechenden Berechtigung auf nativen Code zugreifen kann. Zum Ausführen von nicht typsicherem Code muss die <xref:System.Security.Permissions.SecurityPermission> mit dem übergebenen Enumerationsmember <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A> erteilt werden.  
  
 Weitere Informationen finden Sie unter [Code Access Security Basics](../../framework/misc/code-access-security-basics.md).  
  
## <a name="principal"></a>Prinzipal  
 Ein Prinzipal stellt die Identität und die Rolle eines Benutzers dar und handelt stellvertretend für den Benutzer. Die rollenbasierte Sicherheit in .NET Framework unterstützt drei Arten von Prinzipals:  
  
- Allgemeine Prinzipals stellen Benutzer und Rollen dar, die unabhängig von Benutzern und Rollen unter Windows vorhanden sind.  
  
- Windows-Prinzipals stellen Windows-Benutzer und ihre Rollen bzw. ihre Windows-Gruppen dar. Ein Windows-Prinzipal kann einen anderen Benutzer imitieren, d. h., der Prinzipal kann im Namen eines Benutzers auf eine Ressource zugreifen, wenn er die Identität dieses Benutzers darstellt.  
  
- Benutzerdefinierte Prinzipals können von einer Anwendung je nach Bedarf beliebig definiert werden. Sie können die grundlegenden Eigenschaften der Identität und der Rollen des Prinzipals erweitern.  
  
 Weitere Informationen finden Sie unter [Prinzipal- und Identitätsobjekte](principal-and-identity-objects.md).  
  
## <a name="authentication"></a>Authentifizierung  
 Bei der Authentifizierung wird die Identität eines Prinzipals anhand der Anmeldeinformationen des Benutzers abgerufen und überprüft. Anschließend wird die Gültigkeit dieser Anmeldeinformationen mithilfe einer autorisierten Stelle überprüft. Die bei der Authentifizierung abgerufenen Informationen können vom Code direkt verwendet werden. Sie können den aktuellen Benutzer auch mit der rollenbasierten Sicherheit von .NET Framework authentifizieren und festlegen, ob der Prinzipal auf Ihren Code zugreifen kann. Beispiele zur Authentifizierung des Prinzipals für bestimmte Rollen finden Sie in den Überladungen der <xref:System.Security.Principal.WindowsPrincipal.IsInRole%2A?displayProperty=nameWithType>-Methode. Sie können z. B. mit der <xref:System.Security.Principal.WindowsPrincipal.IsInRole%28System.String%29?displayProperty=nameWithType>-Überladung ermitteln, ob der aktuelle Benutzer Mitglied der Administratorgruppe ist.  
  
 Derzeit werden verschiedene Authentifizierungsverfahren eingesetzt, von denen viele mit der rollenbasierten Sicherheit in .NET Framework verwendet werden können. Am häufigsten werden Standard-, Digest-, Passport- und Betriebssystemverfahren (z. B. NTLM oder Kerberos) sowie anwendungsdefinierte Verfahren verwendet.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel muss der aktive Prinzipal ein Administrator sein. Der `name`-Parameter ist `null`, sodass die Anforderung von allen Benutzern übergeben werden kann, die Administratoren sind.  
  
> [!NOTE]
> Unter Windows Vista werden die Berechtigungen eines Benutzers über die Benutzerkontensteuerung (User Account Control, UAC) bestimmt. Als Mitglied der integrierten Administratorgruppe sind Ihnen zwei Zugriffstoken für die Laufzeit zugewiesen: ein Standardbenutzertoken und ein Administratorzugriffstoken. Standardmäßig verwenden Sie die Standardbenutzerrolle. Um Code ausführen zu können, der Administratorberechtigungen erfordert, müssen Sie zuerst Ihre Berechtigungen von Standardbenutzer auf Administrator erhöhen. Dazu starten Sie eine Anwendung, indem Sie mit der rechten Maustaste auf das Anwendungssymbol klicken und angeben, dass Sie die Anwendung als Administrator ausführen möchten.   
  
 [!code-cpp[Classic PrincipalPermission Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CPP/source.cpp#1)]
 [!code-csharp[Classic PrincipalPermission Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CS/source.cs#1)]
 [!code-vb[Classic PrincipalPermission Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/VB/source.vb#1)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie die Identität des Prinzipals sowie der Rollen bestimmt wird, die für den Prinzipal verfügbar sind. Eine Anwendungsmöglichkeit für dieses Beispiel könnte darin bestehen, zu überprüfen, ob die Rolle des aktuellen Benutzers für die Verwendung der Anwendung zulässig ist.  
  
 [!code-cpp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CPP/source.cpp#1)]
 [!code-csharp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CS/source.cs#1)]
 [!code-vb[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/VB/source.vb#1)]  
  
## <a name="authorization"></a>Authorization  
 Bei der Autorisierung wird bestimmt, ob das Ausführen einer angeforderten Aktion durch einen Prinzipal zulässig ist. Die Autorisierung findet nach der Authentifizierung statt. Sie bestimmt anhand der Informationen zur Identität und Rollen des Prinzipals, auf welche Ressourcen dieser zugreifen darf. Autorisierung können Sie in .NET Framework mithilfe der rollenbasierten Sicherheit implementieren.
