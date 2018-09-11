---
title: Principal- und Identitätsobjekte
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- WindowsIdentity objects
- GenericIdentity objects
- GenericPrincipal objects
- identity objects, about identity objects
- security [.NET Framework], identity objects
- principal objects, about principal objects
- security [.NET Framework], principals
- WindowsPrincipal objects
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8c7616a3187cd5fa28f231dffd15b0bfeea4b7f
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338771"
---
# <a name="principal-and-identity-objects"></a>Principal- und Identitätsobjekte
Verwalteter Code kann ermitteln, die Identität oder Rolle eines Prinzipals über ein <xref:System.Security.Principal.IPrincipal> -Objekt, das enthält einen Verweis auf ein <xref:System.Security.Principal.IIdentity> Objekt. Es kann hilfreich sein, Identity- und Principal-Objekte (Identitäts- und Prinzipalobjekte) mit vertrauten Konzepten wie Benutzer- und Gruppenkonten zu vergleichen. In den meisten Netzwerkumgebungen entsprechen Benutzerkonten Personen oder Programmen und Gruppenkonten bestimmten Kategorien von Benutzern sowie den Rechten, die diese haben. Ähnlich entsprechen Identitätsobjekte in .NET Framework Benutzern, während Rollen Mitgliedschaften und Sicherheitskontexten entsprechen. In .NET Framework kapselt das Prinzipalobjekt sowohl ein Identitätsobjekt als auch eine Rolle. .NET Framework-Anwendungen gewähren dem Prinzipal gemäß seiner Identität oder, dies ist häufiger der Fall, gemäß seiner Rolle bestimmte Rechte.  
  
## <a name="identity-objects"></a>Identitätsobjekte  
 Ein Identitätsobjekt kapselt Informationen über den zu prüfenden Benutzer bzw. die zu prüfende Entität. Identitätsobjekte enthalten in ihrer einfachsten Form einen Namen und einen Authentifizierungstyp. Der Name kann ein Benutzername oder der Name eines Windows-Kontos sein, und der Authentifizierungstyp kann entweder ein unterstütztes Anmeldeprotokoll, z. B. Kerberos V5, oder ein benutzerdefinierter Wert sein. .NET Framework definiert einen <xref:System.Security.Principal.GenericIdentity> -Objekt, das für die meisten benutzerdefinierten Anmeldeszenarios und eine spezifischere verwendet werden kann <xref:System.Security.Principal.WindowsIdentity> -Objekt, das verwendet werden kann, wenn Sie Ihre Anwendung auf der Windows-Authentifizierung verwenden möchten. Zusätzlich können Sie eine eigene Identitätsklasse definieren, die benutzerdefinierte Benutzerinformationen kapselt.  
  
 Die <xref:System.Security.Principal.IIdentity> -Schnittstelle definiert Eigenschaften für den Zugriff auf einen Namen und einen Authentifizierungstyp an, wie z. B. Kerberos V5 oder NTLM. Alle **Identity**-Klassen implementieren die **IIdentity**-Schnittstelle. Es ist keine Beziehung zwischen einem **Identity**-Objekt und dem Windows NT-Prozesstoken erforderlich, unter dem ein Thread aktuell ausgeführt wird. Wenn das **Identity**-Objekt aber ein **WindowsIdentity**-Objekt ist, wird davon ausgegangen, dass die Identität ein Windows NT-Sicherheitstoken darstellt.  
  
## <a name="principal-objects"></a>Prinzipalobjekte  
 Ein Prinzipalobjekt stellt den Sicherheitskontext dar, in dem der Code ausgeführt wird. Anwendungen, die rollenbasierte Sicherheit implementieren, gewähren Rechte anhand der Rolle, die einem Prinzipalobjekt zugeordnet ist. Vergleichbar mit identätsobjekten, .NET Framework bietet eine <xref:System.Security.Principal.GenericPrincipal> Objekt und ein <xref:System.Security.Principal.WindowsPrincipal> Objekt. Sie können auch benutzerdefinierte Prinzipalklassen definieren.  
  
 Die <xref:System.Security.Principal.IPrincipal> -Schnittstelle definiert eine Eigenschaft für den Zugriff auf ein zugeordnetes **Identität** -Objekt sowie eine Methode um zu bestimmen, ob der Benutzer durch identifiziert die **Principal** Objekt ist ein Mitglied einer Rolle. Alle **Principal**-Klassen implementieren die **IPrincipal**-Schnittstelle sowie alle zusätzlichen Eigenschaften und Methoden, die erforderlich sind. Die Common Language Runtime stellt z. B. die **WindowsPrincipal**-Klasse bereit, die zusätzliche Funktionen zum Zuordnen von Windows NT- oder Windows 2000-Gruppenmitgliedschaften zu Rollen implementiert.  
  
 Ein **Principal** ein Aufrufkontext-Objekt gebunden ist (<xref:System.Runtime.Remoting.Messaging.CallContext>) innerhalb einer Anwendungsdomäne (<xref:System.AppDomain>). Mit jeder neuen **AppDomain** wird ein Standardaufrufkontext erstellt, sodass immer ein Aufrufkontext verfügbar ist, um das **Principal**-Objekt zu akzeptieren. Wenn ein neuer Thread erstellt wird, wird für diesen ebenfalls ein neues **CallContext**-Objekt erstellt. Der Verweis auf das **Principal**-Objekt wird automatisch aus dem erstellenden Thread in den **CallContext** des neuen Threads kopiert. Wenn die Runtime nicht bestimmen kann, welches **Principal**-Objekt zum Ersteller des Threads gehört, wird die Standardrichtlinie für die Erstellung von **Principal**- und **Identity**-Objekten angewendet.  
  
 Eine konfigurierbare anwendungsdomänenspezifische Richtlinie definiert die Regeln, nach denen bestimmt wird, welcher Typ von **Principal**-Objekt einer neuen Anwendungsdomäne zuzuordnen ist. Sofern die Sicherheitsrichtlinie dies zulässt, kann die Runtime **Principal**-Objekte und **Identity**-Objekte erstellen, die das Betriebssystemtoken wiedergeben, das dem aktuellen Ausführungsthread zugeordnet ist. Standardmäßig verwendet die Runtime **Principal**-Objekte und **Identity**-Objekte, die nicht authentifizierte Benutzer darstellen. Die Runtime erstellt diese **Principal**- und **Identity**-Standardobjekte erst dann, wenn im Code versucht wird, auf diese zuzugreifen.  
  
 Vertrauenswürdiger Code, der eine Anwendungsdomäne erstellt, kann die Anwendungsdomänenrichtlinie festlegen, die das Erstellen der **Principal**- und **Identity**-Standardobjekte steuert. Diese anwendungsdomänenspezifische Richtlinie gilt für alle Ausführungsthreads in dieser Anwendungsdomäne. Ein nicht verwalteter vertrauenswürdiger Host ist die Möglichkeit, diese Richtlinie festzulegen, verwalteter Code, der mit dieser Richtlinie wird benötigen jedoch die <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> Domänenrichtlinie steuern.  
  
 Wird ein **Principal**-Objekt zwischen Anwendungsdomänen, aber im selben Prozesses (und daher auf demselben Computer) übertragen, kopiert die Remoteinfrastruktur einen Verweis auf das **Principal**-Objekt, das dem Kontext des Aufrufers zugeordnet ist, in den Kontext des Aufgerufenen.  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Erstellen eines WindowsPrincipal-Objekts](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)  
- [Gewusst wie: Erstellen von GenericPrincipal-Objekten und GenericIdentity-Objekten](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)  
- [Ersetzen eines Principalobjekts](../../../docs/standard/security/replacing-a-principal-object.md)  
- [Wechseln und Zurücksetzen der Identität](../../../docs/standard/security/impersonating-and-reverting.md)  
- [Rollenbasierte Sicherheit](../../../docs/standard/security/role-based-security.md)  
- [Schlüsselbegriffe der Sicherheit](../../../docs/standard/security/key-security-concepts.md)
