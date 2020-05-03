---
title: 'Exemplarische Vorgehensweise: Ausgeben von Code in Szenarios mit teilweiser Vertrauenswürdigkeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection emit, anonymously hosted dynamic methods
- partial trust, reflection
- partial trust, emitting dynamic methods
- reflection emit, partial trust scenarios
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
ms.openlocfilehash: fd420c9754494b95c55df403edec87743572db03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129993"
---
# <a name="walkthrough-emitting-code-in-partial-trust-scenarios"></a>Exemplarische Vorgehensweise: Ausgeben von Code in Szenarios mit teilweiser Vertrauenswürdigkeit

Die Reflektionsausgabe verwendet für volle oder teilweise Vertrauenswürdigkeit den gleichen API-Satz, für teilweise vertrauenswürdigen Code erfordern einige Funktionen allerdings besondere Berechtigungen. Außerdem verfügt die Reflektionsausgabe über eine Funktion für anonym gehostete dynamische Methoden, die zur Verwendung mit teilweiser Vertrauenswürdigkeit und sicherheitstransparenten Assemblys vorgesehen ist.

> [!NOTE]
> Vor .NET Framework 3.5 war zur Ausgabe von Code <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType>-Flag erforderlich. Diese Berechtigung ist standardmäßig im benannten `FullTrust`- und `Intranet`-Berechtigungssatz enthalten, jedoch nicht im `Internet`-Berechtigungssatz. Daher kann eine Bibliothek nur mit teilweiser Vertrauenswürdigkeit verwendet werden, wenn sie über das <xref:System.Security.SecurityCriticalAttribute>-Attribut verfügt und eine <xref:System.Security.PermissionSet.Assert%2A>-Methode für <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit> ausgeführt hat. Diese Bibliotheken erfordern einen sorgfältigen Sicherheitsreview, da Codierungsfehler zu Sicherheitslücken führen können. In .NET Framework 3.5 ist es möglich, Code in teilweise vertrauenswürdigen Szenarios ohne Sicherheitsanforderungen auszugeben, da das Generieren von Code an sich keinen privilegierten Vorgang darstellt. Das bedeutet, dass der generierte Code nicht mehr Berechtigungen aufweist als die Assembly, die ihn ausgibt. Bibliotheken, die Code ausgeben, können somit sicherheitstransparent sein und setzen keine <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>-Assertion voraus, sodass zum Schreiben einer sicheren Bibliothek keine genaue Sicherheitsüberprüfung erforderlich ist.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:

- [Das Einrichten einer einfachen Sandkastenanwendung zum Testen von teilweise vertrauenswürdigem Code](#Setting_up)

  > [!IMPORTANT]
  > Dies ist eine einfache Möglichkeit zum Experimentieren mit teilweise vertrauenswürdigem Code. Informationen zum Ausführen von Code, der aus nicht vertrauenswürdigen Speicherorten stammt, finden Sie unter [Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

- [Ausführen von Code in teilweise vertrauenswürdigen Anwendungsdomänen](#Running_code)

- [Verwenden von anonym gehosteten dynamischen Methoden zum Ausgeben und Ausführen von Code in Szenarios mit teilweiser Vertrauenswürdigkeit](#Using_methods)

Weitere Informationen zum Ausgeben von Code in Szenarios mit teilweiser Vertrauenswürdigkeit finden Sie unter [Security Issues in Reflection Emit (Sicherheitsaspekte bei der Reflektionsausgabe)](security-issues-in-reflection-emit.md).

Eine vollständige Auflistung des in diesen Verfahren dargestellten Codes finden Sie im [Beispielabschnitt](#Example) am Ende dieser exemplarischen Vorgehensweise.

<a name="Setting_up"></a>

## <a name="setting-up-partially-trusted-locations"></a>Einrichten von teilweise vertrauenswürdigen Speicherorten

Die folgenden beiden Verfahren enthalten Informationen zum Einrichten von Speicherorten, über die teilweise vertrauenswürdiger Code getestet werden kann.

- Im ersten Verfahren wird beschrieben, wie Sie eine Sandboxanwendungsdomäne erstellen, in der dem Code Internetberechtigungen zugewiesen werden.

- Im zweiten Verfahren wird beschrieben, wie Sie einer teilweise vertrauenswürdigen Anwendungsdomäne <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag hinzufügen, um Zugriff auf private Daten in Assemblys mit gleicher oder geringerer Vertrauenswürdigkeit zu ermöglichen.

### <a name="creating-sandboxed-application-domains"></a>Erstellen von Sandbox-Anwendungsdomänen

Um eine Anwendungsdomäne zu erstellen, in der Ihre Assemblys mit teilweiser Vertrauenswürdigkeit ausgeführt werden, müssen Sie den Satz der Berechtigungen, die den Assemblys erteilt werden sollen, mithilfe der <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Methodenüberladung angeben. Am einfachsten ist es, einen benannten Berechtigungssatz aus der Sicherheitsrichtlinie abzurufen.

Im folgenden Verfahren wird eine Sandbox-Anwendungsdomäne erstellt, die Code mit teilweiser Vertrauenswürdigkeit ausführt, um Szenarios zu testen, in denen ausgegebener Code nur auf öffentliche Member öffentlicher Typen zugreifen kann. In einem späteren Verfahren wird beschrieben, wie Sie <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> hinzufügen, um Szenarios zu testen, in denen ausgegebener Code auf nicht öffentliche Typen und Member in Assemblys zugreifen kann, denen die gleichen oder geringere Berechtigungen erteilt wurden.

#### <a name="to-create-an-application-domain-with-partial-trust"></a>So erstellen Sie eine Anwendungsdomäne mit teilweiser Vertrauenswürdigkeit

1. Erstellen Sie einen Berechtigungssatz, der den Assemblys in der Sandkastenanwendungsdomäne gewährt wird. In diesem Fall wird der Berechtigungssatz der Internetzone verwendet.

    [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
    [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]

2. Erstellen Sie ein <xref:System.AppDomainSetup>-Objekt, um die Anwendungsdomäne mit einem Anwendungspfad zu initialisieren.

    > [!IMPORTANT]
    > In diesem Codebeispiel wird der Einfachheit halber der aktuelle Ordner verwendet. Um Code auszuführen, der eigentlich aus dem Internet stammt, verwenden Sie einen separaten Ordner für den nicht vertrauenswürdigen Code, wie in [Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md) beschrieben.

    [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
    [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]

3. Erstellen Sie die Anwendungsdomäne, indem Sie die Setupinformationen der Anwendungsdomäne und den Berechtigungssatz für alle Assemblys angeben, die in der Anwendungsdomäne ausgeführt werden.

    [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
    [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]

    Mit dem letzten Parameter der <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Methodenüberladung können Sie anstelle des Berechtigungssatzes der Anwendungsdomäne eine Gruppe von Assemblys angeben, denen volle Vertrauenswürdigkeit erteilt werden soll. Die von der Anwendung verwendeten .NET Framework-Assemblys müssen Sie nicht angeben, da diese Assemblys im globalen Assemblycache enthalten sind. Assemblys im globalen Assemblycache sind immer voll vertrauenswürdig. Sie können diesen Parameter verwenden, um Assemblys mit starkem Namen anzugeben, die nicht im globalen Assemblycache enthalten sind.

### <a name="adding-restrictedmemberaccess-to-sandboxed-domains"></a>Hinzufügen von eingeschränktem Memberzugriff auf Sandboxdomänen

Hostanwendungen können anonym gehosteten dynamischen Methoden Zugriff auf private Daten in Assemblys ermöglichen, die die gleiche oder eine geringere Vertrauensebene als die Assembly aufweisen, die den Code ausgibt. Um diese eingeschränkte Fähigkeit zum Überspringen von JIT-Sichtbarkeitsprüfungen zu ermöglichen, fügt die Hostanwendung dem Berechtigungssatz ein <xref:System.Security.Permissions.ReflectionPermission>-Objekt mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag hinzu.

Beispielsweise kann ein Host Internetanwendungen sowohl Internetberechtigungen als auch eingeschränkten Memberzugriff (RestrictedMemberAccess, RMA) erteilen, sodass eine Internetanwendung Code ausgeben kann, der auf private Daten in den eigenen Assemblys zugreift. Da der Zugriff auf Assemblys mit gleicher oder geringerer Vertrauenswürdigkeit beschränkt ist, kann eine Internetanwendung nicht auf Member voll vertrauenswürdiger Assemblys zugreifen, z. B. .NET Framework-Assemblys.

> [!NOTE]
> Um Rechteerweiterungen zu verhindern, werden beim Erstellen anonym gehosteter dynamischer Methoden Stapelinformationen für die ausgebende Assembly einbezogen. Wenn die Methode aufgerufen wird, werden die Stapelinformationen überprüft. Daher ist eine anonym gehostete dynamische Methode, die über voll vertrauenswürdigen Code aufgerufen wird, auf die Vertrauensebene der ausgebenden Assembly beschränkt.

#### <a name="to-create-an-application-domain-with-partial-trust-plus-rma"></a>So erstellen Sie eine Anwendungsdomäne mit teilweiser Vertrauenswürdigkeit und eingeschränktem Memberzugriff

1. Erstellen Sie ein neues <xref:System.Security.Permissions.ReflectionPermission>-Objekt mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> (RMA)-Flag, und fügen Sie die Berechtigung mit der <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=nameWithType>-Methode dem Berechtigungssatz hinzu.

    [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
    [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]

    Wenn die Berechtigung noch nicht im Berechtigungssatz enthalten ist, wird sie mit der <xref:System.Security.PermissionSet.AddPermission%2A>-Methode hinzugefügt. Wenn die Berechtigung bereits im Berechtigungssatz enthalten ist, werden die angegebenen Flags der vorhandenen Berechtigung hinzugefügt.

    > [!NOTE]
    > Das Feature des eingeschränkten Memberzugriffs ist ein Feature anonym gehosteter dynamischer Methoden. Wenn gewöhnliche dynamische Methoden die JIT-Sichtbarkeitsüberprüfungen überspringen, erfordert der ausgegebene Code volle Vertrauenswürdigkeit.

2. Erstellen Sie die Anwendungsdomäne, indem Sie die Setupinformationen für die Anwendungsdomäne und den Berechtigungssatz angeben.

    [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
    [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]

<a name="Running_code"></a>

## <a name="running-code-in-sandboxed-application-domains"></a>Ausführen von Code in Sandbox-Anwendungsdomänen

Im folgenden Verfahren wird beschrieben, wie Sie eine Klasse mit Methoden definieren, die in einer Anwendungsdomäne ausgeführt werden können, wie Sie eine Instanz dieser Klasse in der Domäne erstellen und wie Sie deren Methoden ausführen.

#### <a name="to-define-and-execute-a-method-in-an-application-domain"></a>So definieren Sie eine Methode in einer Anwendungsdomäne und führen sie aus

1. Definieren Sie eine Klasse, die sich von <xref:System.MarshalByRefObject> ableitet. Auf diese Weise können Sie Instanzen der Klasse in anderen Anwendungsdomänen erstellen und Methoden über die Grenzen der Anwendungsdomäne hinweg aufrufen. Die Klasse in diesem Beispiel hat den Namen `Worker`.

    [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
    [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]

2. Definieren Sie eine öffentliche Methode, die den Code enthält, den Sie ausführen möchten. In diesem Beispiel gibt der Code eine einfache dynamische Methode aus, erstellt einen Delegaten zum Ausführen der Methode und ruft den Delegaten auf.

    [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
    [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]

3. Rufen Sie im Hauptprogramm den Anzeigenamen der Assembly ab. Dieser Name wird verwendet, wenn Sie Instanzen der `Worker`-Klasse in der Sandbox-Anwendungsdomäne erstellen.

    [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
    [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]

4. Erstellen Sie im Hauptprogramm eine Sandbox-Anwendungsdomäne, wie in der [ersten Prozedur](#Setting_up) dieser exemplarischen Vorgehensweise beschrieben. Sie müssen dem `Internet`-Berechtigungssatz keine Berechtigungen hinzufügen, da die `SimpleEmitDemo`-Methode nur öffentliche Methoden verwendet.

5. Erstellen Sie im Hauptprogramm eine Instanz der `Worker`-Klasse in der Sandbox-Anwendungsdomäne.

    [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
    [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]

    Die <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>-Methode erstellt das Objekt in der Zielanwendungsdomäne und gibt einen Proxy zurück, der zum Aufrufen der Eigenschaften und Methoden des Objekts verwendet werden kann.

    > [!NOTE]
    > Wenn Sie diesen Code in Visual Studio verwenden, müssen Sie den Namen der Klasse ändern, sodass der Namespace enthalten ist. Standardmäßig ist der Namespace der Name des Projekts. Wenn das Projekt z. B. "PartialTrust" heißt, muss der Klassenname "PartialTrust.Worker" lauten.

6. Fügen Sie Code zum Aufrufen der `SimpleEmitDemo`-Methode hinzu. Der Aufruf wird über die Grenze der Anwendungsdomäne hinweg gemarshallt, und der Code wird in der Sandbox-Anwendungsdomäne ausgeführt.

    [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
    [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]

<a name="Using_methods"></a>

## <a name="using-anonymously-hosted-dynamic-methods"></a>Verwenden von anonym gehosteten dynamischen Methoden

Anonym gehostete dynamische Methoden werden einer transparenten Assembly zugeordnet, die vom System bereitgestellt wird. Daher ist der Code, den sie enthalten, transparent. Gewöhnliche dynamische Methoden müssen andererseits einem vorhandenen Modul (das entweder direkt angegeben oder von einem zugeordneten Typ abgeleitet wird) zugeordnet sein und übernehmen ihre Sicherheitsstufe von diesem Modul.

> [!NOTE]
> Die einzige Möglichkeit, der Assembly, die anonymes Hosting bereitstellt, eine dynamische Methode zuzuordnen, ist die Verwendung der in den folgenden Verfahren beschriebenen Konstruktoren. Es ist nicht möglich, ein Modul in der anonymen Hostingassembly explizit anzugeben.

Normale dynamische Methoden verfügen über Zugriff auf die internen Member des Moduls, dem sie zugeordnet sind, oder auf die privaten Member des Typs, dem sie zugeordnet sind. Da anonym gehostete dynamische Methoden von anderem Code isoliert sind, verfügen sie über keinen Zugriff auf private Daten. Sie besitzen jedoch die eingeschränkte Fähigkeit, JIT-Sichtbarkeitsprüfungen zu überspringen, um Zugriff auf private Daten zu erhalten. Diese Möglichkeit ist auf Assemblys beschränkt, die die gleiche oder eine geringere Vertrauensebene aufweisen als die Assembly, die den Code ausgibt.

Um Rechteerweiterungen zu verhindern, werden beim Erstellen anonym gehosteter dynamischer Methoden Stapelinformationen für die ausgebende Assembly einbezogen. Wenn die Methode aufgerufen wird, werden die Stapelinformationen überprüft. Eine anonym gehostete dynamische Methode, die über voll vertrauenswürdigen Code aufgerufen wird, ist auf die Vertrauensebene der ausgebenden Assembly beschränkt.

#### <a name="to-use-anonymously-hosted-dynamic-methods"></a>So verwenden Sie anonym gehostete dynamische Methoden

- Erstellen Sie eine anonym gehostete dynamische Methode, indem Sie einen Konstruktor verwenden, der kein zugeordnetes Modul und keinen zugeordneten Typ angibt.

  [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
  [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]

  Wenn eine anonym gehostete dynamische Methode nur öffentliche Typen und Methoden verwendet, erfordert sie keinen eingeschränkten Memberzugriff und muss keine JIT-Sichtbarkeitsprüfungen überspringen.

  Zur Ausgabe einer dynamischen Methode sind keine speziellen Berechtigungen erforderlich. Der ausgegebene Code erfordert jedoch die Berechtigungen, die von den verwendeten Typen und Methoden verlangt werden. Wenn der ausgegebene Code z. B. eine Methode aufruft, die auf eine Datei zugreift, erfordert er <xref:System.Security.Permissions.FileIOPermission>. Wenn diese Berechtigung in der Vertrauensebene nicht enthalten ist, wird eine Sicherheitsausnahme ausgelöst, sobald der ausgegebene Code ausgeführt wird. Der hier dargestellte Code gibt eine dynamische Methode aus, die nur die <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>-Methode verwendet. Daher kann der Code über teilweise vertrauenswürdige Speicherorte ausgeführt werden.

- Alternativ können Sie eine anonym gehostete dynamische Methode mit eingeschränkter Fähigkeit zum Überspringen von JIT-Sichtbarkeitsprüfungen erstellen, indem Sie den <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29>-Konstruktor verwenden und `true` für den `restrictedSkipVisibility`-Parameter angeben.

  [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
  [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]

  Die Einschränkung besteht darin, dass die anonym gehostete dynamische Methode nur auf private Daten in Assemblys zugreifen kann, die die gleiche oder eine geringere Vertrauensebene als die ausgebende Assembly aufweisen. Wenn die dynamische Methode z. B. mit Internet-Vertrauenswürdigkeit ausgeführt wird, kann sie auf private Daten in Assemblys zugreifen, die ebenfalls mit Internet-Vertrauenswürdigkeit ausgeführt werden, aber nicht auf private Daten in .NET Framework-Assemblys. .NET Framework-Assemblys werden im globalen Assemblycache installiert und sind immer voll vertrauenswürdig.

  Anonym gehostete dynamische Methoden können diese eingeschränkte Fähigkeit zum Überspringen von JIT-Sichtbarkeitsprüfungen nur verwenden, wenn die Hostanwendung <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag erteilt. Diese Berechtigung wird angefordert, wenn die Methode aufgerufen wird.

  > [!NOTE]
  > Beim Erstellen der dynamischen Methode werden Aufruflisteninformationen für die ausgebende Assembly einbezogen. Daher bezieht sich die Anforderung auf die Berechtigungen der ausgebenden Assembly und nicht der Assembly, die die Methode aufruft. Somit wird verhindert, dass der ausgegebene Code mit erweiterten Berechtigungen ausgeführt wird.

  Das [vollständige Codebeispiel](#Example) am Ende dieser exemplarischen Vorgehensweise veranschaulicht die Verwendung und die Einschränkungen des eingeschränkten Memberzugriffs. Die dort verwendete `Worker`-Klasse beinhaltet eine Methode, die anonym gehostete dynamische Methoden mit oder ohne eingeschränkte Fähigkeit zum Überspringen von Sichtbarkeitsprüfungen erstellen kann. Das Beispiel zeigt das Ergebnis der Ausführung dieser Methode in Anwendungsdomänen mit verschiedenen Vertrauensebenen.

  > [!NOTE]
  > Die eingeschränkte Fähigkeit zum Überspringen von Sichtbarkeitsprüfungen ist ein Feature anonym gehosteter dynamischer Methoden. Wenn gewöhnliche dynamische Methoden die JIT-Sichtbarkeitsprüfungen überspringen, muss ihnen volle Vertrauenswürdigkeit gewährt werden.

<a name="Example"></a>

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Codebeispiel veranschaulicht die Verwendung des <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess>-Flags, um anonym gehosteten dynamischen Methoden das Überspringen von JIT-Sichtbarkeitsprüfungen zu ermöglichen, wenn der Zielmember die gleiche oder eine geringere Vertrauensebene aufweist als die Assembly, die den Code ausgibt.

Im Beispiel wird eine `Worker`-Klasse definiert, die über die Grenzen der Anwendungsdomäne hinweg gemarshallt werden kann. Die Klasse verfügt über zwei `AccessPrivateMethod`-Methodenüberladungen, die dynamische Methoden ausgeben und ausführen. Die erste Überladung gibt eine dynamische Methode (mit oder ohne JIT-Sichtbarkeitsprüfungen) aus, die die private `PrivateMethod`-Methode der `Worker`-Klasse aufruft. Die zweite Überladung gibt eine dynamische Methode aus, die auf eine `internal`-Eigenschaft (`Friend`-Eigenschaft in Visual Basic) der <xref:System.String>-Klasse zugreift.

In dem Beispiel wird mit einer Hilfsmethode ein Berechtigungssatz erstellt, der auf die `Internet`-Berechtigungen begrenzt ist. Anschließend wird eine Anwendungsdomäne erstellt, wobei mit der <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Methodenüberladung angegeben wird, dass der gesamte Code, der in der Domäne ausgeführt wird, diesen Berechtigungssatz verwendet. Außerdem wird eine Instanz der `Worker`-Klasse in der Anwendungsdomäne erstellt und die `AccessPrivateMethod`-Methode zweimal ausgeführt.

- Bei der ersten Ausführung der `AccessPrivateMethod`-Methode werden JIT-Sichtbarkeitsprüfungen erzwungen. Die dynamische Methode schlägt fehl, wenn sie aufgerufen wird, da sie durch JIT-Sichtbarkeitsprüfungen daran gehindert wird, auf die private Methode zuzugreifen.

- Bei der zweiten Ausführung der `AccessPrivateMethod`-Methode werden JIT-Sichtbarkeitsprüfungen übersprungen. Die dynamische Methode schlägt fehl, wenn sie kompiliert wird, da der `Internet`-Berechtigungssatz keine ausreichenden Berechtigungen zum Überspringen von Sichtbarkeitsprüfungen bereitstellt.

In diesem Beispiel wird dem Berechtigungssatz <xref:System.Security.Permissions.ReflectionPermission> mit <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> hinzugefügt. Anschließend wird eine zweite Domäne erstellt, wobei dem gesamten Code, der in der Domäne ausgeführt wird, die Berechtigungen im neuen Berechtigungssatz erteilt werden. Zusätzlich wird eine Instanz der `Worker`-Klasse in der neuen Anwendungsdomäne erstellt, und es werden beide Überladungen der `AccessPrivateMethod`-Methode ausgeführt.

- Die erste Überladung der `AccessPrivateMethod`-Methode wird ausgeführt, und JIT-Sichtbarkeitsprüfungen werden übersprungen. Die dynamische Methode wird erfolgreich kompiliert und ausgeführt, da die Assembly, die den Code ausgibt, mit der Assembly identisch ist, die die private Methode enthält. Daher sind die Vertrauensebenen gleich. Wenn die Anwendung, die die `Worker`-Klasse enthält, über mehrere Assemblys verfügen würde, wäre der gleiche Prozess für jede dieser Assemblys erfolgreich, da sie alle die gleiche Vertrauensebene aufweisen würden.

- Die zweite Überladung der `AccessPrivateMethod`-Methode wird ausgeführt, und JIT-Sichtbarkeitsprüfungen werden erneut übersprungen. Dieses Mal schlägt die dynamische Methode beim Kompilieren fehl, da sie versucht, auf die `internal``FirstChar`-Eigenschaft der <xref:System.String>-Klasse zuzugreifen. Die Assembly, die die <xref:System.String>-Klasse enthält, ist voll vertrauenswürdig. Somit weist sie eine höhere Vertrauensebene auf als die Assembly, die den Code ausgibt.

Dieser Vergleich zeigt, wie teilweise vertrauenswürdiger Code durch <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> Sichtbarkeitsprüfungen für anderen teilweise vertrauenswürdigen Code überspringen kann, ohne die Sicherheit von vertrauenswürdigem Code zu gefährden.

### <a name="code"></a>Code

[!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
[!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

- Wenn Sie dieses Codebeispiel in Visual Studio verwenden, müssen Sie den Namespace in den Namen der Klasse einbeziehen, wenn Sie diese an die <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>-Methode übergeben. Standardmäßig ist der Namespace der Name des Projekts. Wenn das Projekt z. B. "PartialTrust" heißt, muss der Klassenname "PartialTrust.Worker" lauten.

## <a name="see-also"></a>Siehe auch

- [Sicherheitsaspekte bei der Reflektionsausgabe](security-issues-in-reflection-emit.md)
- [How to: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
