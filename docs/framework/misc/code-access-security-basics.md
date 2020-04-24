---
title: Grundlagen der Codezugriffssicherheit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], code access security
ms.assetid: 4eaa6535-d9fe-41a1-91d8-b437cfc16921
ms.openlocfilehash: 352fa41cb9d3136f853b068d0101a6dcab5dfd7c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645772"
---
# <a name="code-access-security-basics"></a>Grundlagen der Codezugriffssicherheit

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Jede Anwendung für die Common Language Runtime (also jede verwaltete Anwendung) muss mit dem Sicherheitssystem der Runtime interagieren. Wenn eine verwaltete Anwendung geladen wird, gewährt der Host ihr automatisch einen Satz von Berechtigungen. Diese Berechtigungen werden von den lokalen Sicherheitseinstellungen des Hosts oder von der Sandbox bestimmt, in der die Anwendung enthalten ist. In Abhängigkeit von diesen Berechtigungen wird die Anwendung ordnungsgemäß ausgeführt, oder es wird eine Sicherheitsausnahme generiert.

Der Standardhost für Desktopanwendungen ermöglicht, dass Code mit voller Vertrauenswürdigkeit ausgeführt wird. Wenn die Anwendung für den Desktop konzipiert ist, hat sie daher einen uneingeschränkten Berechtigungssatz. Andere Hosts oder Sandboxes stellen für Anwendungen einen eingeschränkten Berechtigungssatz bereit. Da sich der Berechtigungssatz von Host zu Host unterscheiden kann, müssen Sie Ihre Anwendung so entwerfen, dass sie nur die vom Zielhost zugelassenen Berechtigungen verwendet.

Sie müssen mit den folgenden Konzepten der Codezugriffssicherheit vertraut sein, um effiziente Anwendungen für die Common Language Runtime schreiben zu können:

- **Typsicherer Code**: Typsicherer Code ist Code, der nur auf klar definierte, zulässige Weise auf Typen zugreift. Beispielsweise kann typsicherer Code, wenn ein gültiger Objektverweis angegeben ist, an festen Offsets, die tatsächlichen Feldmembern entsprechen, auf Speicher zugreifen. Greift der Code auf Speicher an beliebigen Offsets zu, die sich außerhalb des Speicherbereichs befinden, der zu den öffentlich verfügbar gemachten Feldern dieses Objekts gehört, ist er nicht typsicher. Um für Code ein Profitieren von Codezugriffssicherheit zu ermöglichen, müssen Sie einen Compiler verwenden, der nachweisbar typsicheren Code generiert. Weitere Informationen finden Sie im Abschnitt Schreiben von [prüfbarem Typsicherer Code](#typesafe_code) weiter unten in diesem Thema.

- **Imperative und deklarative Syntax**: Code, der auf die Common Language Runtime abzielt, kann mit dem Sicherheitssystem interagieren, indem Berechtigungen angefordert, gefordert wird, dass Aufrufer über bestimmte Berechtigungen verfügen, und bestimmte Sicherheitseinstellungen außer Kraft setzen (mit ausreichenden Berechtigungen). Für die programmgesteuerte Interaktion mit dem Sicherheitssystem von .NET Framework verwenden Sie zwei verschiedene Syntaxformen: die deklarative und die imperative Syntax. Deklarative Aufrufe werden mithilfe von Attributen ausgeführt, imperative Aufrufe werden mit neuen Instanzen von Klassen im Code ausgeführt. Einige Aufrufe können nur imperativ ausgeführt werden, andere können nur deklarativ ausgeführt werden, und einige Aufrufe können auf beide Arten ausgeführt werden.

- **Sichere Klassenbibliotheken:** Eine sichere Klassenbibliothek verwendet Sicherheitsanforderungen, um sicherzustellen, dass die Aufrufer der Bibliothek über die Berechtigung zum Zugriff auf die Ressourcen verfügen, die die Bibliothek verfügbar macht. Eine sichere Klassenbibliothek kann z. B. eine Methode zum Erstellen von Dateien haben, in der gefordert wird, dass ihre Aufrufer Berechtigungen zum Erstellen von Dateien haben. .NET Framework besteht aus sicheren Klassenbibliotheken. Sie müssen die Berechtigungen berücksichtigen, die für Zugriffe auf jede Bibliothek erforderlich sind, die in Ihrem Code verwendet wird. Weitere Informationen finden Sie im Abschnitt [Verwenden sicherer Klassenbibliotheken](#secure_library) weiter unten in diesem Thema.

- **Transparenter Code:** Beginnend mit .NET Framework 4 müssen Sie neben dem Identifizieren bestimmter Berechtigungen auch bestimmen, ob der Code als sicherheitstransparent ausgeführt werden soll. Aus sicherheitstransparentem Code können weder Typen oder Member aufgerufen werden, die als sicherheitskritisch gekennzeichnet sind. Diese Regel gilt sowohl für voll vertrauenswürdige Anwendungen als auch für teilweise vertrauenswürdige Anwendungen. Weitere Informationen finden Sie unter [Sicherheitstransparenter Code](security-transparent-code.md).

<a name="typesafe_code"></a>

## <a name="writing-verifiably-type-safe-code"></a>Schreiben von überprüfbar typsicherem Code

Bei der Just-in-Time-Kompilierung (JIT) wird ein Überprüfungsverfahren angewendet, in dem Code untersucht und versucht wird, zu ermitteln, ob der Code typsicher ist. Code, der sich bei der Überprüfung als typsicher erwiesen hat, wird als *überprüfbarer typsicherer Code*bezeichnet. Wegen der Beschränkungen des Überprüfungsverfahrens oder des Compilers kann Code typsicher, jedoch möglicherweise nicht überprüfbar typsicher sein. Nicht alle Sprachen sind typsicher, und einige Sprachcompiler, z. B. Microsoft Visual C++, können keinen überprüfbar typsicheren verwalteten Code generieren. Um festzustellen, ob der von Ihnen verwendete Sprachcompiler überprüfbar typsicheren Code generiert, lesen Sie die entsprechenden Informationen in der Dokumentation des Compilers. Wenn Sie einen Sprachcompiler verwenden, der nur dann nachweisbar typsicheren Code generiert, wenn Sie bestimmte Sprachkonstrukte vermeiden, sollten Sie mit dem [PEVerify-Tool](../tools/peverify-exe-peverify-tool.md) ermitteln, ob der Code nachweisbar typsicher ist.

Code, der nicht überprüfbar typsicher ist, kann versuchen, ausgeführt zu werden, wenn die Sicherheitsrichtlinie zulässt, dass der Code die Überprüfung umgeht. Da Typsicherheit aber ein wesentlicher Bestandteil des Runtime-Mechanismus zur Isolation von Assemblys ist, kann Sicherheit nicht zuverlässig erzwungen werden, wenn die Regeln für die Typsicherheit durch Code verletzt werden. In der Standardeinstellung kann Code, der nicht typsicher ist, nur ausgeführt werden, wenn er vom lokalen Computer stammt. Aus diesem Grund sollte mobiler Code typsicher sein.

<a name="secure_library"></a>

## <a name="using-secure-class-libraries"></a>Verwenden von sicheren Klassenbibliotheken

Wenn Ihr Code die Berechtigungen anfordert und erhält, die von der Klassenbibliothek gefordert werden, wird ihm der Zugriff auf die Bibliothek gewährt, und die Ressourcen, die von der Bibliothek verfügbar gemacht werden, werden vor nicht autorisiertem Zugriff geschützt. Wenn Ihr Code nicht die entsprechenden Berechtigungen hat, wird ihm kein Zugriff auf die Klassenbibliothek gewährt, und Schadsoftware ist nicht in der Lage, den Code zu verwenden, um indirekt auf geschützte Ressourcen zuzugreifen. Anderer Code, der Ihren Code aufruft, muss ebenfalls die Berechtigung zum Zugriff auf die Bibliothek haben. Ist dies nicht der Fall ist, wird auch die Ausführung Ihres Code entsprechend eingeschränkt.

Codezugriffssicherheit verhindert nicht, dass Sie möglicherweise fehlerhaften Code schreiben. Wenn Ihre Anwendung jedoch mithilfe von sicheren Klassenbibliotheken auf geschützte Ressourcen zugreift, ist das Sicherheitsrisiko für Anwendungscode geringer, da Klassenbibliotheken eingehend auf mögliche Sicherheitsprobleme überprüft werden.

## <a name="declarative-security"></a>Deklarative Sicherheit

Die deklarative Sicherheitssyntax verwendet [Attribute,](../../standard/attributes/index.md) um Sicherheitsinformationen in den [Metadaten](../../standard/metadata-and-self-describing-components.md) des Codes zu platzieren. Attribute können auf Assembly-, Klassen- oder Memberebene platziert werden, um den Typ der Anforderung, Forderung oder Überschreibung zu kennzeichnen, die Sie verwenden möchten. Anforderungen werden in Anwendungen für die Common Language Runtime verwendet, um das Runtime-Sicherheitssystem über die Berechtigungen zu informieren, die Ihre Anwendung benötigt bzw. nicht wünscht. Forderungen und Überschreibungen werden in Bibliotheken verwendet, um Ressourcen vor Aufrufern zu schützen oder Standardsicherheitsverhalten zu überschreiben.

> [!NOTE]
> In .NET Framework 4 wurden wichtige Änderungen am .NET Framework-Sicherheitsmodell und der Terminologie vorgenommen. Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).

Damit Sie Aufrufe für deklarative Sicherheit verwenden können, müssen Sie die Zustandsdaten des Berechtigungsobjekts so initialisieren, dass sie der bestimmten Form von Berechtigung entsprechen, die Sie benötigen. Jede integrierte Berechtigung hat ein Attribut, das als eine <xref:System.Security.Permissions.SecurityAction>-Enumeration übergeben wird, um den Typ des Sicherheitsvorgangs zu beschreiben, den Sie ausführen möchten. Berechtigungen akzeptieren auch ihre eigenen Parameter, die ihnen exklusiv zugewiesen sind.

Das folgende Codefragment veranschaulicht deklarative Syntax zum Anfordern, dass Aufrufer Ihres Codes eine benutzerdefinierte Berechtigung namens `MyPermission` haben. Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden. In diesem Beispiel befindet sich der deklarative Aufruf direkt vor der Klassendefinition, wodurch angegeben ist, dass diese Berechtigung auf Klassenebene angewendet wird. Das Attribut wird an eine **SecurityAction.Demand-Struktur** übergeben, um anzugeben, dass Aufrufer über diese Berechtigung verfügen müssen, um ausgeführt werden zu können.

```vb
<MyPermission(SecurityAction.Demand, Unrestricted = True)> Public Class MyClass1

   Public Sub New()
      'The constructor is protected by the security call.
   End Sub

   Public Sub MyMethod()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'This method is protected by the security call.
   End Sub
End Class
```

```csharp
[MyPermission(SecurityAction.Demand, Unrestricted = true)]
public class MyClass
{
   public MyClass()
   {
      //The constructor is protected by the security call.
   }

   public void MyMethod()
   {
      //This method is protected by the security call.
   }

   public void YourMethod()
   {
      //This method is protected by the security call.
   }
}
```

## <a name="imperative-security"></a>Imperative Sicherheit

Imperative Sicherheitssyntax gibt einen Sicherheitsaufruf aus, indem eine neuen Instanz des Berechtigungsobjekts erstellt wird, das Sie aufrufen möchten. Über imperative Syntax können Sie Forderungen und Überschreibungen, aber keine Anforderungen ausführen.

Bevor Sie den Sicherheitsaufruf vornehmen, müssen Sie die Zustandsdaten des Berechtigungsobjekts so initialisieren, dass sie der bestimmten Form von Berechtigung entsprechen, die Sie benötigen. Wenn Sie beispielsweise <xref:System.Security.Permissions.FileIOPermission> ein Objekt erstellen, können Sie den Konstruktor verwenden, um das **FileIOPermission-Objekt** so zu initialisieren, dass es entweder uneingeschränkten Zugriff auf alle Dateien oder keinen Zugriff auf Dateien darstellt. Sie können auch ein anderes **FileIOPermission-Objekt** verwenden, indem Sie Parameter übergeben, die den Zugriffstyp angeben, den das Objekt darstellen soll (d. h. lesen, anhängen oder schreiben) und welche Dateien das Objekt schützen soll.

Imperative Sicherheitssyntax kann nicht nur zum Aufrufen eines einzelnen Sicherheitsobjekts verwendet werden, sondern auch dazu, eine Gruppe von Berechtigungen in einem Berechtigungssatz zu initialisieren. Diese Technik ist z. B. die einzige Möglichkeit, [Assertionsaufrufe](using-the-assert-method.md) für mehrere Berechtigungen in einer Methode zuverlässig auszuführen. Verwenden Sie die Klassen <xref:System.Security.PermissionSet> und <xref:System.Security.NamedPermissionSet>, um eine Gruppe von Berechtigungen zu erstellen, und rufen Sie anschließend die entsprechende Methode auf, um den gewünschten Sicherheitsaufruf auszuführen.

Über imperative Syntax können Sie Forderungen und Überschreibungen, aber keine Anforderungen ausführen. Sie können imperative Syntax für Forderungen und Überschreibungen anstelle von deklarativer Syntax verwenden, wenn die Informationen, die Sie benötigen, um den Berechtigungsstatus initialisieren, nur zur Laufzeit bekannt sind. Wenn Sie beispielsweise sicherstellen möchten, dass Aufrufer die Berechtigung zum Lesen einer bestimmten Datei haben, der Name dieser Datei aber erst zur Laufzeit bekannt ist, verwenden Sie eine imperative Forderung. Sie können auch imperative Überprüfungen anstelle von deklarativen Überprüfungen verwenden, wenn Sie zur Laufzeit bestimmen müssen, ob eine Bedingung zutrifft, und dann basierend auf dem Ergebnis des Tests eine Sicherheitsforderung stellen (oder nicht).

Das folgende Codefragment veranschaulicht imperative Syntax zum Anfordern, dass Aufrufer Ihres Codes eine benutzerdefinierte Berechtigung namens `MyPermission` haben. Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden. Es wird eine neue Instanz von `MyPermission` erstellt, `MyMethod`, die ausschließlich diese Methode mit dem Sicherheitsaufruf schützt.

```vb
Public Class MyClass1

   Public Sub New()

   End Sub

   Public Sub MyMethod()
      'MyPermission is demanded using imperative syntax.
      Dim Perm As New MyPermission()
      Perm.Demand()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'YourMethod 'This method is not protected by the security call.
   End Sub
End Class
```

```csharp
public class MyClass {
   public MyClass(){

   }

   public void MyMethod() {
       //MyPermission is demanded using imperative syntax.
       MyPermission Perm = new MyPermission();
       Perm.Demand();
       //This method is protected by the security call.
   }

   public void YourMethod() {
       //This method is not protected by the security call.
   }
}
```

## <a name="using-managed-wrapper-classes"></a>Verwenden von verwalteten Wrapperklassen

Die meisten Anwendungen und Komponenten (mit Ausnahme von sicheren Bibliotheken) sollten nicht verwalteten Code nicht direkt aufrufen. Hierfür gibt es mehrere Gründe: Wenn Code nicht verwalteten Code direkt aufruft, wird seine Ausführung häufig nicht zugelassen, weil Code ein hohes Maß an Vertrauenswürdigkeit gewährt werden muss, damit er nativen Code aufrufen kann. Wird die Richtlinie so geändert, dass sie das Ausführen einer solchen Anwendung zulässt, kann die Sicherheit des Systems deutlich geschwächt werden, weil die Anwendung Gelegenheit erhält, nahezu jede Operation auszuführen.

Darüber hinaus kann Code, der die Berechtigung zum Zugriff auf nicht verwalteten Code hat, wahrscheinlich fast jeden Vorgang ausführen, indem er Code in einer nicht verwalteten API aufruft. Beispielsweise muss <xref:System.Security.Permissions.FileIOPermission> Code, der über die Berechtigung zum Aufrufen von nicht verwaltetem Code verfügt, nicht auf eine Datei zugreifen. Es kann einfach eine nicht verwaltete (Win32) Datei-API direkt aufrufen und dabei die verwaltete Datei-API umgehen, die **FileIOPermission**erfordert. Wenn verwalteter Code die Berechtigung zum Aufrufen von nicht verwaltetem Code hat, kann das Sicherheitssystem Sicherheitsbeschränkungen nicht zuverlässig erzwingen, da die Runtime solche Beschränkungen für nicht verwalteten Code nicht erzwingen kann.

Soll Ihre Anwendung einen Vorgang ausführen, der Zugriff auf nicht verwalteten Code erfordert, sollte dieser Zugriff über eine vertrauenswürdige verwaltete Klasse erfolgen, die die benötigten Funktionalität umschließt (sofern eine solche Klasse vorhanden ist). Sie sollten nicht selbst eine Wrapperklasse erstellen, wenn es eine solche bereits in einer sicheren Klassenbibliothek gibt. Die Wrapperklasse, der ein hohes Maß an Vertrauenswürdigkeit gewährt werden muss, damit Sie den Aufruf von nicht verwaltetem Code vornehmen darf, ist dafür verantwortlich, von ihren Aufrufern zu fordern, dass sie die entsprechenden Berechtigungen haben. Wenn Sie die Wrapperklasse verwenden, muss der Code nur die Berechtigungen anfordern und erhalten, die von der Wrapperklasse gefordert werden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.NamedPermissionSet>
- <xref:System.Security.Permissions.SecurityAction>
- [Assert](using-the-assert-method.md)
- [Codezugriffssicherheit](code-access-security.md)
- [Grundlagen der Codezugriffssicherheit](code-access-security-basics.md)
- [Attribute](../../standard/attributes/index.md)
- [Metadaten und selbstbeschreibende Komponenten](../../standard/metadata-and-self-describing-components.md)
