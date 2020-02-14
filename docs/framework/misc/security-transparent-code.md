---
title: Sicherheitstransparenter Code
ms.date: 03/30/2017
helpviewer_keywords:
- transparent code
- security-transparent code
ms.assetid: 4f3dd841-82f7-4659-aab0-6d2db2166c65
ms.openlocfilehash: ca251ec3084d40269b107e7bd8bef708e8d49622
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215834"
---
# <a name="security-transparent-code"></a>Sicherheitstransparenter Code

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Sicherheit schließt drei interagierende Elemente ein: Sandkasten, Berechtigungen und Erzwingung. Unter einem Sandkasten versteht man das Erstellen isolierter Domänen, in denen bestimmter Code als vollständig vertrauenswürdig und sonstiger Code auf die Berechtigungen im Berechtigungssatz für den Sandkasten beschränkt ist. Der Anwendungscode, der innerhalb des Berechtigungssatzes des Sandkastens ausgeführt wird, wird als transparent betrachtet, das heißt, es können keine Vorgänge ausgeführt werden, die sich auf die Sicherheit auswirken können. Der Berechtigungssatz für den Sandkasten wird durch Beweis bestimmt (<xref:System.Security.Policy.Evidence>-Klasse). Beweise geben Aufschluss darüber, welche bestimmten Berechtigungen von Sandkästen benötigt werden, und welche Arten von Sandkästen erstellt werden. Erzwingung bedeutet, dass transparenter Code nur innerhalb seines Berechtigungssatzes ausgeführt werden darf.

> [!IMPORTANT]
> Die Sicherheitsrichtlinie war ein Schlüsselelement in früheren Versionen von .NET Framework. Ab .NET Framework 4 ist die Sicherheitsrichtlinie veraltet. Die Beseitigung der Sicherheitsrichtlinie geschieht getrennt von der Sicherheitstransparenz. Informationen zu den Auswirkungen dieser Änderung finden Sie unter [Kompatibilität und Migration von Richtlinien für die Code Zugriffssicherheit](code-access-security-policy-compatibility-and-migration.md).

## <a name="purpose-of-the-transparency-model"></a>Zweck des Transparenzmodells

Transparenz ist ein Erzwingungsmechanismus, mit dem Code, der als Teil der Anwendung von Code ausgeführt wird, der wiederum als Teil der Infrastruktur ausgeführt wird. Transparenz unterscheidet zwischen Code, in dem privilegierte Aktionen wie das Aufrufen von systemeigenem Code ausgeführt werden können (sicherheitsrelevanter Code), und Code, in dem dies nicht möglich ist (transparenter Code). In transparentem Code können Befehle in den Grenzen des Berechtigungssatzes, in denen der Code verwendet wird, ausgeführt werden. Es ist jedoch nicht möglich, dass mit transparentem Code wichtiger Code ausgeführt und davon abgeleitet wird bzw. er darf keinen wichtigen Code enthalten.

Das primäre Ziel der Transparenzerzwingung besteht darin, einen einfachen, effektiven Mechanismus für die Isolation verschiedener Codegruppen auf Grundlage von Rechten bereitzustellen. Innerhalb des Kontexts des Sandkastenmodells sind diese Rechtegruppen entweder voll vertrauenswürdig (das heißt, sie unterliegen keine Einschränkungen) oder teilweise vertrauenswürdig (das heißt, sie sind auf den Berechtigungssatz beschränkt, der dem Sandkasten gewährt wurde).

> [!IMPORTANT]
> Das Transparenzmodell geht über Codezugriffssicherheit hinaus. Transparenz wird vom Just-In-Time-Compiler erzwungen und bleibt unabhängig vom Berechtigungssatz für eine Assembly in Kraft, einschließlich vollständiger Vertrauenswürdigkeit.

Transparenz wurde in .NET Framework, Version 2.0, eingeführt, um das Sicherheitsmodell zu vereinfachen und das Schreiben und Bereitstellen von sicheren Bibliotheken und Anwendungen zu erleichtern. Transparenter Code wird auch in Microsoft Silverlight verwendet, um die Entwicklung von teilweise vertrauenswürdigen Anwendungen zu vereinfachen.

> [!NOTE]
> Wenn Sie eine teilweise vertrauenswürdige Anwendung entwickeln, beachten Sie die Berechtigungsanforderungen für die Zielhosts. Sie können eine Anwendung entwickeln, die Ressourcen verwendet, die von einigen Hosts nicht zugelassen werden. Diese Anwendung wird ohne Fehler kompiliert, schlägt jedoch fehl, wenn sie in die gehostete Umgebung geladen wird. Wenn Sie die Anwendung mit Visual Studio entwickelt haben, können Sie in der Entwicklungsumgebung das Debuggen in teilweiser Vertrauenswürdigkeit oder in einem eingeschränkten Berechtigungssatz aktivieren. Weitere Informationen finden Sie unter [Gewusst wie: Debuggen einer ClickOnce-Anwendung mit eingeschränkten Berechtigungen](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions). Die für ClickOnce-Anwendungen bereitgestellte Funktion zur Berechnung von Berechtigungen ist auch für jede beliebige teilweise vertrauenswürdige Anwendung verfügbar.

## <a name="specifying-the-transparency-level"></a>Angeben der Transparenzebene

Das <xref:System.Security.SecurityRulesAttribute>-Attribut auf Assemblyebene wählt explizit die <xref:System.Security.SecurityRuleSet>-Regeln aus, nach denen sich die Assembly richtet. Die Regeln werden unter einem System mit numerischen Ebenen organisiert, wobei höhere Ebenen eine strengere Erzwingung von Sicherheitsregeln bedeuten.

Die Ebenen lauten folgendermaßen:

- Ebene 2 (<xref:System.Security.SecurityRuleSet.Level2>) – die Transparenzregeln .NET Framework 4.

- Ebene 1 (<xref:System.Security.SecurityRuleSet.Level1>) – die .NET Framework 2.0-Transparenzregeln.

Der primäre Unterschied zwischen den zwei Transparenzebenen besteht darin, dass auf Ebene 1 keine Transparenzregeln für Aufrufe von außerhalb der Assembly erzwungen werden und dass diese Ebene nur für Kompatibilität vorgesehen ist.

> [!IMPORTANT]
> Geben Sie Transparenz der Ebene 1 nur für Kompatibilität an, das heißt, geben Sie Ebene 1 nur für Code an, der mit .NET Framework 3.5 oder niedriger entwickelt wurde und für den das <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut verwendet bzw. für den das Transparenzmodell nicht verwendet wird. Verwenden Sie Transparenz der Ebene 1 z. B. für .NET Framework 2.0-Assemblys, die Aufrufe von teilweise vertrauenswürdigen Aufrufern (APTCA) ermöglichen. Verwenden Sie für Code, der für die .NET Framework 4 entwickelt wurde, immer Transparenz der Ebene 2.

### <a name="level-2-transparency"></a>Transparenz der Ebene 2

Transparenz der Ebene 2 wurde in der .NET Framework 4 eingeführt. Die drei Grundsätze dieses Modells sind transparenter Code, sicherheitsgeschützter Code und sicherheitskritischer Code.

- Transparenter Code kann unabhängig von den Berechtigungen, die er erhält (einschließlich vollständiger Vertrauenswürdigkeit), nur anderen transparenten Code oder sicherheitsgeschützten Code aufrufen. Wenn der Code teilweise vertrauenswürdig ist, können nur Aktionen ausgeführt werden, die gemäß dem Berechtigungssatz der Domäne zulässig sind. Transparenter Code ist nicht für die folgenden Vorgänge vorgesehen:

  - Ausführen eines <xref:System.Security.CodeAccessPermission.Assert%2A>-Vorgangs oder einer Berechtigungserweiterung.

  - Der Code darf keinen unsicheren oder nicht überprüfbaren Code enthalten.

  - Direktes Aufrufen von wichtigem Code.

  - Aufrufen von systemeigenen Code oder von Code, der das <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>-Attribut besitzt.

  - Aufrufen eines Members, der von einem <xref:System.Security.Permissions.SecurityAction.LinkDemand>-Feld geschützt wird.

  - Erben von wichtigen Typen.

    Außerdem können transparente Methoden keine wichtigen virtuellen Methoden überschreiben oder wichtige Schnittstellenmethoden implementieren.

- Sicherheitsgeschützter Code ist vollständig vertrauenswürdig, kann aber durch transparenten Code aufgerufen werden. Es macht einen beschränkten Oberflächenbereich mit vollständig vertrauenswürdigen Codes verfügbar. Korrektheits- und Sicherheitsüberprüfungen werden in sicherheitsgeschütztem Code ausgeführt.

- Mit sicherheitskritischem Code kann jeder Code aufgerufen werden, und er ist vollständig vertrauenswürdig, kann jedoch nicht von transparentem Code aufgerufen werden.

### <a name="level-1-transparency"></a>Transparenz der Ebene 1

Das Transparenzmodell der Ebene 1 wurde in .NET Framework, Version 2.0, eingeführt, um es Entwicklern zu ermöglichen, die Codemenge zu reduzieren, die Sicherheitsüberwachung unterliegt. Obwohl Transparenz der Ebene 1 in Version 2.0 öffentlich verfügbar war, wurde sie hauptsächlich nur bei Microsoft für Sicherheitsüberwachungszwecke verwendet. Mit Anmerkungen können Entwickler deklarieren, welche Typen und Member Sicherheitserweitungen und andere vertrauenswürdige Aktionen ausführen können (sicherheitsrelevant) und welche nicht (sicherheitstransparent). Code, der als transparent gekennzeichnet ist, erfordert keine umfassende Sicherheitsüberwachung. Transparenz der Ebene 1 gibt an, dass die Transparenzerzwingung auf die Assembly beschränkt ist. Anders ausgedrückt sind alle öffentlichen Typen oder Member, die als sicherheitskritisch eingestuft werden, nur innerhalb der Assembly sicherheitskritisch. Wenn Sie Sicherheit für diese Typen und die Member erzwingen möchten, wenn sie von außerhalb der Assembly aufgerufen werden, müssen Sie Linkaufrufe für volle Vertrauenswürdigkeit verwenden. Wenn dies nicht der Fall ist, werden öffentlich sichtbare sicherheitskritische Typen und Member als sicherheitsgeschützt behandelt und von teilweise vertrauenswürdigem Code außerhalb der Assembly aufgerufen.

Für das Transparenzmodell der Ebene 1 gelten die folgenden Einschränkungen:

- Auf sicherheitskritische Typen und Member, die öffentlich sind, kann von sicherheitstransparentem Code zugegriffen werden.

- Die Transparenzanmerkungen werden nur innerhalb einer Assembly erzwungen.

- Sicherheitskritische Typen und Member müssen Sicherheit für Aufrufe von außerhalb der Assembly mithilfe von Linkaufrufen erzwingen.

- Vererbungsregeln werden nicht erzwungen.

- Es besteht die Möglichkeit, dass durch transparenten Code schädliche Vorgänge ausgeführt werden, wenn er mit voller Vertrauenswürdigkeit ausgeführt wird.

## <a name="transparency-enforcement"></a>Transparenzerzwingung

Transparenzregeln werden erst erzwungen, wenn Transparenz berechnet wird. Zu diesem Zeitpunkt wird eine <xref:System.InvalidOperationException> ausgelöst, wenn gegen eine Transparenzregel verstoßen wird. Die Zeit zur Berechnung der Transparenz hängt von mehreren Faktoren ab und kann nicht vorhergesagt werden. Sie wird so spät wie möglich berechnet. Im .NET Framework 4 erfolgt die Berechnung der Transparenz auf Assemblyebene früher als in der .NET Framework 2,0. Es ist nur garantiert, dass die Transparenzberechnung ausgeführt wird, wenn sie benötigt wird. Dies ist vergleichbar mit der Änderung des Punkts durch den Just-In-Time-Compiler, an dem eine Methode kompiliert wird und Fehler in dieser Methode erkannt werden. Die Transparenzberechnung ist unsichtbar, wenn der Code keine Transparenzfehler enthält.

## <a name="see-also"></a>Weitere Informationen

- [Sicherheits transparenter Code, Ebene 1](security-transparent-code-level-1.md)
- [Sicherheits transparenter Code, Ebene 2](security-transparent-code-level-2.md)
