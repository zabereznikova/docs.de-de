---
title: Erweitern des My-Namespace
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 2a7b0b84061fccd9a333a68e4a19477bd19ca4ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330315"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Erweitern des `My`-Namespace in Visual Basic

Der `My`-Namespace in Visual Basic stellt Eigenschaften und Methoden bereit, mit denen Sie die Leistungsfähigkeit von .NET Framework problemlos nutzen können. Der `My`-Namespace vereinfacht häufig auftretende Programmierprobleme, wodurch oft eine schwierige Aufgabe auf eine einzelne Codezeile reduziert werden kann. Außerdem ist der `My`-Namespace vollständig erweiterbar, sodass Sie das Verhalten von `My` anpassen und neue Dienste zur Hierarchie hinzufügen können, damit er spezifischen Anwendungsanforderungen entspricht. In diesem Thema wird erläutert, wie vorhandene Member des `My`-Namespace angepasst und eigene benutzerdefinierte Klassen zum `My`-Namespace hinzugefügt werden können.

## <a name="customizing-existing-my-namespace-members"></a>Anpassen vorhandener `My`-Namespacemember

Der `My`-Namespace in Visual Basic stellt häufig verwendete Informationen zu Ihrer Anwendung, Ihrem Computer und vielem mehr bereit. Eine komplette Liste der Objekte im `My`-Namespace finden Sie unter [My-Referenz](../../language-reference/keywords/my-reference.md). Möglicherweise müssen Sie vorhandene Member des `My`-Namespace anpassen, damit diese den Anforderungen Ihrer Anwendung besser entsprechen. Jede Eigenschaft eines Objekts im `My`-Namespace, die nicht schreibgeschützt ist, kann auf einen benutzerdefinierten Wert festgelegt werden.

Angenommen, Sie verwenden häufig das Objekt `My.User`, um auf den aktuellen Sicherheitskontext für den Benutzer zuzugreifen, der Ihre Anwendung ausführt. Ihr Unternehmen verwendet jedoch ein benutzerdefiniertes Benutzerobjekt, um zusätzliche Informationen und Funktionen für Benutzer innerhalb des Unternehmens verfügbar zu machen. In diesem Szenario können Sie den Standardwert der Eigenschaft `My.User.CurrentPrincipal` durch eine Instanz Ihres eigenen benutzerdefinierten Prinzipalobjekts ersetzen, wie im folgenden Beispiel gezeigt:

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

Wenn Sie die `CurrentPrincipal`-Eigenschaft für das `My.User`-Objekt festlegen, ändert sich die Identität, unter der die Anwendung ausgeführt wird. Das `My.User`-Objekt wiederum gibt Informationen zum neu angegebenen Benutzer zurück.
  
## <a name="adding-members-to-my-objects"></a>Hinzufügen von Membern zu `My`-Objekten

Die von `My.Application` und `My.Computer` zurückgegebenen Typen sind als `Partial`-Klassen definiert. Aus diesem Grund können Sie die Objekte `My.Application` und `My.Computer` erweitern, indem Sie eine `Partial`-Klasse mit dem Namen `MyApplication` bzw. `MyComputer` erstellen. Die Klasse kann keine `Private`-Klasse sein. Wenn Sie die Klasse als Teil des `My`-Namespace angeben, können Sie Eigenschaften und Methoden hinzufügen, die in die Objekte `My.Application` oder `My.Computer` aufgenommen werden.

Im folgenden Beispiel wird eine Eigenschaft mit dem Namen `DnsServerIPAddresses` zum `My.Computer`-Objekt hinzugefügt:

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>Hinzufügen benutzerdefinierter Objekte zum `My`-Namespace

Obwohl der `My`-Namespace Lösungen für viele gängige Programmieraufgaben bereitstellt, können Sie auf Aufgaben stoßen, die der `My`-Namespace nicht abdeckt. Beispielsweise kann Ihre Anwendung auf benutzerdefinierte Verzeichnisdienste für Benutzerdaten zugreifen, oder die Anwendung verwendet Assemblys, die nicht standardmäßig mit Visual Basic installiert werden. Sie können den `My`-Namespace erweitern, um benutzerdefinierte Lösungen für häufige Aufgaben zu integrieren, die für Ihre Umgebung spezifisch sind. Der `My`-Namespace kann problemlos erweitert werden, um neue Member hinzuzufügen und so wachsende Anwendungsanforderungen zu erfüllen. Darüber hinaus können Sie Ihre `My`-Namespaceerweiterungen anderen Entwicklern als Visual Basic-Vorlage bereitstellen.
  
### <a name="adding-members-to-the-my-namespace"></a>Hinzufügen von Membern zum `My`-Namespace

Da `My` ein Namespace wie jeder andere ist, können Sie ihm Eigenschaften der obersten Ebene hinzufügen. Dazu fügen Sie einfach ein Modul hinzu und geben einen `Namespace` vom Typ `My` an. Versehen Sie das Modul mit dem Attribut `HideModuleName`, wie es im folgenden Beispiel gezeigt ist. Durch das `HideModuleName`-Attribut wird sichergestellt, dass IntelliSense den Modulnamen nicht anzeigt, wenn die Member des `My`-Namespace angezeigt werden.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

Um dem `My`-Namespace Member hinzuzufügen, fügen Sie dem Modul nach Bedarf Eigenschaften hinzu. Fügen Sie für jede Eigenschaft, die dem `My`-Namespace hinzugefügt wird, ein privates Feld vom Typ `ThreadSafeObjectProvider(Of T)` hinzu, wobei der Typ der von der benutzerdefinierten Eigenschaft zurückgegebene Typ ist. Mithilfe dieses Felds werden threadsichere Objektinstanzen erstellt, die durch Aufrufen der `GetInstance`-Methode von der Eigenschaft zurückgegeben werden. Folglich erhält jeder Thread, der auf die erweiterte Eigenschaft zugreift, eine eigene Instanz des zurückgegebenen Typs. Im folgenden Beispiel wird eine Eigenschaft mit dem Namen `SampleExtension` vom Typ `SampleExtension` zum `My`-Namespace hinzugefügt:

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>Hinzufügen von Ereignissen zu benutzerdefinierten `My`-Objekten

Mithilfe des `My.Application`-Objekts können Sie Ereignisse für Ihre benutzerdefinierten `My`-Objekte bereitstellen, indem Sie die partielle Klasse `MyApplication` im `My`-Namespace erweitern. Bei Windows-basierten Projekten können Sie im **Projektmappen-Explorer** auf den Knoten **Mein Projekt** für Ihr Projekt doppelklicken. Klicken Sie im **Projekt-Designer** von Visual Basic auf die Registerkarte **Anwendung** und dann auf die Schaltfläche **Anwendungsereignisse anzeigen**. Eine neue Datei mit dem Namen *ApplicationEvents.vb* wird erstellt. Sie enthält den folgenden Code zum Erweitern der `MyApplication`-Klasse:

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

Sie können Ereignishandler für Ihre benutzerdefinierten `My`-Objekte hinzufügen, indem Sie der `MyApplication`-Klasse benutzerdefinierte Ereignishandler hinzufügen. Mithilfe von benutzerdefinierten Ereignissen können Sie Code hinzufügen, der dann ausgeführt wird, wenn ein Ereignishandler hinzugefügt oder entfernt oder das Ereignis ausgelöst wird. Beachten Sie, dass der `AddHandler`-Code für ein benutzerdefiniertes Ereignis nur dann ausgeführt wird, wenn der Code von einem Benutzer zur Behandlung des Ereignisses hinzufügt wird. Angenommen, das `SampleExtension`-Objekt aus dem vorherigen Abschnitt weist ein `Load`-Ereignis auf, für das Sie einen benutzerdefinierten Ereignishandler hinzufügen möchten. Das folgende Codebeispiel zeigt einen benutzerdefinierten Ereignishandler mit dem Namen `SampleExtensionLoad`, der bei Auftreten des Ereignisses `My.SampleExtension.Load` aufgerufen wird. Wenn Code zur Behandlung des neuen `My.SampleExtensionLoad`-Ereignisses hinzugefügt wird, wird der `AddHandler`-Teil dieses benutzerdefinierten Ereigniscodes ausgeführt. Die Methode `MyApplication_SampleExtensionLoad` ist im Codebeispiel enthalten, um ein Beispiel für einen Ereignishandler zu zeigen, der das Ereignis `My.SampleExtensionLoad` behandelt. Beachten Sie, dass das `SampleExtensionLoad`-Ereignis verfügbar ist, wenn Sie beim Bearbeiten der Datei *ApplicationEvents.vb* oberhalb des Code-Editors in der linken Dropdownliste die Option **Meine Anwendungsereignisse** auswählen.

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>Entwurfsrichtlinien

Verwenden Sie beim Entwickeln von Erweiterungen für den `My`-Namespace die folgenden Richtlinien, um die Wartungskosten der Erweiterungskomponenten zu minimieren:

- **Schließen Sie nur die Erweiterungslogik ein.** Die in der `My`-Namespaceerweiterung enthaltene Logik sollte nur den Code umfassen, der benötigt wird, um die erforderliche Funktionalität im `My`-Namespace verfügbar zu machen. Da Ihre Erweiterung in Benutzerprojekten als Quellcode enthalten ist, verursacht das Aktualisieren der Erweiterungskomponente hohe Wartungskosten und sollte nach Möglichkeit vermieden werden.
- **Minimieren Sie Projektannahmen.** Wenn Sie die Erweiterungen des `My`-Namespace erstellen, setzen Sie nicht eine Gruppe von Verweisen, Importe auf Projektebene oder bestimmte Compilereinstellungen (z. B. `Option Strict` deaktiviert) als Annahme voraus. Minimieren Sie stattdessen Abhängigkeiten, und nehmen Sie eine vollständige Qualifizierung aller Typverweise mithilfe des Schlüsselworts `Global` vor. Stellen Sie außerdem sicher, dass die Erweiterung mit aktivierter `Option Strict`-Einstellung kompiliert wird, um Fehler in der Erweiterung zu minimieren.
- **Isolieren Sie den Erweiterungscode.** Wenn Sie den Code in einer einzelnen Datei ablegen, kann Ihre Erweiterung problemlos als Visual Studio-Elementvorlage bereitgestellt werden. Weitere Informationen finden Sie unter „Packen und Bereitstellen von Erweiterungen“ weiter unten in diesem Thema. Wenn Sie den gesamten Code der `My`-Namespaceerweiterung in einer einzelnen Datei oder in einem separaten Ordner in einem Projekt ablegen, können die Benutzer die `My`-Namespaceerweiterung auch leichter finden.

## <a name="designing-class-libraries-for-my"></a>Entwerfen von Klassenbibliotheken für `My`

Wie bei den meisten Objektmodellen funktionieren einige Entwurfsmuster im `My`-Namespace gut und andere nicht. Beachten Sie beim Entwerfen einer Erweiterung für den `My`-Namespace die folgenden Prinzipien:

- **Zustandslose Methoden.** Methoden im `My`-Namespace sollten eine komplette Lösung für eine bestimmte Aufgabe bereitstellen. Stellen Sie sicher, dass die an die Methode übergebenen Parameterwerte sämtliche Eingaben bereitstellen, die zum Ausführen der jeweiligen Aufgabe erforderlich sind. Vermeiden Sie das Erstellen von Methoden, die auf einem vorherigen Zustand beruhen, z. B. offene Verbindungen mit Ressourcen.
- **Globale Instanzen.** Der einzige Zustand, der im `My`-Namespace beibehalten wird, ist für das Projekt global. Beispielsweise kapselt `My.Application.Info` den Zustand, der in der gesamten Anwendung gemeinsam verwendet wird.
- **Einfache Parametertypen.** Vermeiden Sie der Einfachheit halber komplexe Parametertypen. Erstellen Sie stattdessen Methoden, die entweder keine Parametereingaben erfordern oder einfache Eingabetypen wie Zeichenfolgen, primitive Typen usw. akzeptieren.
- **Factorymethoden.** Einige Typen sind notwendigerweise schwer zu instanziieren. Wenn Sie Factorymethoden als Erweiterungen für den `My`-Namespace bereitstellen, können Sie Typen, die in diese Kategorie fallen, leichter ermitteln und nutzen. Ein Beispiel für eine gut funktionierende Factorymethode ist `My.Computer.FileSystem.OpenTextFileReader`. Es sind mehrere Streamtypen in .NET Framework verfügbar. Durch die spezifische Angabe von Textdateien kann der Benutzer mithilfe von `OpenTextFileReader` besser verstehen, welcher Stream zu verwenden ist.

Diese Richtlinien schließen allgemeinen Entwurfsprinzipien für Klassenbibliotheken nicht aus. Vielmehr handelt es sich um optimierte Empfehlungen für Entwickler, die Visual Basic und den `My`-Namespace verwenden. Allgemeine Entwurfsprinzipien zum Erstellen von Klassenbibliotheken finden Sie unter [Framework-Entwurfsrichtlinien](../../../standard/design-guidelines/index.md).

## <a name="packaging-and-deploying-extensions"></a>Packen und Bereitstellen von Erweiterungen

Sie können `My`-Namespaceerweiterungen in eine Visual Studio-Projektvorlage einschließen, oder Sie können Ihre Erweiterungen packen und als Visual Studio-Elementvorlage bereitstellen. Wenn Sie die `My`-Namespaceerweiterungen als Visual Studio-Elementvorlage packen, können Sie zusätzliche Funktionen nutzen, die von Visual Basic bereitgestellt werden. Mithilfe dieser Funktionen können Sie eine Erweiterung einbeziehen, wenn ein Projekt auf eine bestimmte Assembly verweist, oder Benutzern können Ihre `My`-Namespaceeweiterung über die Seite **Meine Erweiterungen**  im Projekt-Designer von Visual Basic explizit hinzufügen.

Ausführliche Informationen zum Bereitstellen von `My`-Namespaceerweiterungen finden Sie unter [Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen](packaging-and-deploying-custom-my-extensions.md).

## <a name="see-also"></a>Siehe auch

- [Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen](packaging-and-deploying-custom-my-extensions.md)
- [Erweitern des Visual Basic-Anwendungsmodells](extending-the-visual-basic-application-model.md)
- [Anpassen der verfügbaren Objekte in „My“](customizing-which-objects-are-available-in-my.md)
- [My-Erweiterungen-Seite im Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../language-reference/modifiers/partial.md)
