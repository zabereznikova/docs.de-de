---
title: "Extending the My Namespace in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.AddingMyExtensions"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My namespace, customizing"
  - "My namespace"
  - "My namespace, extending"
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Extending the My Namespace in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der `My`\-Namespace in Visual Basic macht Eigenschaften und Methoden verfügbar, mit denen Sie alle Vorteile von .NET Framework problemlos nutzen können.  Der `My`\-Namespace vereinfacht häufig auftretende Programmierprobleme und löst schwierige Aufgaben oftmals mit nur einer Codezeile.  Darüber hinaus ist der `My`\-Namespace vollständig erweiterbar. So können Sie das Verhalten von `My` anpassen und seiner Hierarchie neue Dienste hinzufügen, um den Namespace auf spezielle Anwendungsanforderungen abzustimmen.  In diesem Thema wird erläutert, wie vorhandene Member des `My`\-Namespaces angepasst werden und wie Sie dem `My`\-Namespace eigene benutzerdefinierte Klassen hinzufügen.  
  
 **Themeninhalt**  
  
-   [Anpassen von vorhandenen Membern des My\-Namespaces](#customizing)  
  
-   [Hinzufügen von Membern zu My\-Objekten](#addingtoobjects)  
  
-   [Hinzufügen von benutzerdefinierten Objekten zum My\-Namespace](#addingcustom)  
  
-   [Hinzufügen von Membern zum My\-Namespace](#addingtonamespace)  
  
-   [Hinzufügen von Ereignissen zu benutzerdefinierten My\-Objekten](#addingevents)  
  
-   [Entwurfsrichtlinien](#design)  
  
-   [Entwerfen von Klassenbibliotheken für My](#designing)  
  
-   [Verpacken und Bereitstellen von Erweiterungen](#packaging)  
  
##  <a name="customizing"></a> Anpassen von vorhandenen Membern des My\-Namespaces  
 Der `My`\-Namespace in Visual Basic macht häufig verwendete Informationen über die Anwendung, den Computer usw. verfügbar.  Eine vollständige Liste der Objekte im `My`\-Namespace finden Sie unter [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md).  Vorhandene Member des `My`\-Namespaces müssen eventuell angepasst werden, damit sie besser den Anforderungen der Anwendung entsprechen.  Alle nicht schreibgeschützten Eigenschaften von Objekten im `My`\-Namespace können auf einen benutzerdefinierten Wert festgelegt werden.  
  
 Angenommen, Sie verwenden häufig das `My.User`\-Objekt, um auf den aktuellen Sicherheitskontext für den Benutzer zuzugreifen, der Ihre Anwendung ausführt.  Ihr Unternehmen verwendet jedoch ein benutzerdefiniertes Objekt, um Benutzern innerhalb des Unternehmens zusätzliche Informationen und Funktionen zur Verfügung zu stellen.  In diesem Szenario können Sie den Standardwert der `My.User.CurrentPrincipal`\-Eigenschaft durch eine Instanz Ihres eigenen benutzerdefinierten Prinzipalobjekts ersetzen, wie das folgende Beispiel zeigt.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 Wenn die `CurrentPrincipal`\-Eigenschaft des `My.User`\-Objekts festgelegt wird, ändert sich die Identität, unter der die Anwendung ausgeführt wird.  Das `My.User`\-Objekt wiederum gibt Informationen über den neu angegebenen Benutzer zurück.  
  
##  <a name="addingtoobjects"></a> Hinzufügen von Membern zu My\-Objekten  
 Die von `My.Application` und `My.Computer` zurückgegebenen Typen sind als `Partial`\-Klassen definiert.  Daher können Sie das `My.Application`\-Objekt und das `My.Computer`\-Objekt erweitern, indem Sie eine `Partial`\-Klasse mit dem Namen `MyApplication` oder `MyComputer` erstellen.  Bei der Klasse kann es sich nicht um eine `Private`\-Klasse handeln.  Wenn Sie die Klasse als Teil des `My`\-Namespaces angeben, können Sie Eigenschaften und Methoden hinzufügen, die im `My.Application`\-Objekt oder `My.Computer`\-Objekt enthalten sind.  
  
 Im folgenden Beispiel wird z. B. eine Eigenschaft mit dem Namen `DnsServerIPAddresses` zum `My.Computer`\-Objekt hinzugefügt.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> Hinzufügen von benutzerdefinierten Objekten zum My\-Namespace  
 Zwar stellt der `My`\-Namespace Lösungen für häufig auftretende Programmieraufgaben bereit, doch gibt es möglicherweise auch Aufgaben, für die der `My`\-Namespace keine Lösung bietet.  Ihre Anwendung greift z. B. auf benutzerdefinierte Verzeichnisdienste für Benutzerdaten zu, oder die Anwendung verwendet unter Umständen Assemblys, die nicht standardmäßig mit Visual Basis installiert werden.  Sie können den `My`\-Namespace um benutzerdefinierte Lösungen für häufige, speziell in Ihrer Umgebung auszuführende Aufgaben erweitern.  Der `My`\-Namespace kann problemlos um neue Member erweitert werden, um wachsenden Anwendungsanforderungen zu erfüllen.  Darüber hinaus können Sie Ihre `My`\-Namespaceerweiterungen anderen Entwicklern als Visual Basic\-Vorlage bereitstellen.  
  
###  <a name="addingtonamespace"></a> Hinzufügen von Membern zum My\-Namespace  
 Da es sich beim `My`\-Namespace um einen gewöhnlichen Namespace handelt, können Sie ihm Eigenschaften der obersten Ebene hinzufügen. Dazu müssen Sie lediglich ein Modul hinzufügen und einen `Namespace` von `My` angeben.  Kommentieren Sie das Modul mit dem `HideModuleName`\-Attribut, wie im folgenden Beispiel gezeigt.  Das `HideModuleName`\-Attribut stellt sicher, dass der Modulname von IntelliSense nicht angezeigt wird, wenn die Member des `My`\-Namespaces angezeigt werden.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Um dem `My`\-Namespace Member hinzuzufügen, fügen Sie dem Modul Eigenschaften je nach Bedarf hinzu.  Fügen Sie für jede dem `My`\-Namespace hinzugefügte Eigenschaft ein privates Feld vom Typ `ThreadSafeObjectProvider(Of T)` hinzu. Bei dem Typ handelt es sich dabei um den von der benutzerdefinierten Eigenschaft zurückgegebenen Typ.  Dieses Feld dient zum Erstellen threadsicherer Objektinstanzen, die von der Eigenschaft zurückgegeben werden sollen, indem die `GetInstance`\-Methode aufgerufen wird.  Daher empfängt jeder Thread, der auf die erweiterte Eigenschaft zugreift, seine eigene Instanz des zurückgegebenen Typs.  Im folgenden Beispiel wird eine Eigenschaft mit dem Namen `SampleExtension`, die dem Typ `SampleExtension` angehört, zum `My`\-Namespace hinzugefügt:  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> Hinzufügen von Ereignissen zu benutzerdefinierten My\-Objekten  
 Mit dem `My.Application`\-Objekt können Sie Ereignisse für Ihre benutzerdefinierten `My`\-Objekte verfügbar machen, indem Sie die partielle `MyApplication`\-Klasse im `My`\-Namespace erweitern.  Bei Windows\-basierten Projekten können Sie auf den Knoten **Mein Projekt** für das Projekt im **Projektmappen\-Explorer** doppelklicken.  Im Visual Basic\-**Projekt\-Designer** klicken Sie auf die Registerkarte `Application` und dann auf die Schaltfläche `View Application Events`.  Eine neue Datei mit dem Namen ApplicationEvents.vb wird erstellt.  Sie enthält den folgenden Code zum Erweitern der `MyApplication`\-Klasse.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 Sie können Ereignishandler für Ihre benutzerdefinierten `My`\-Objekte hinzufügen, indem Sie der `MyApplication`\-Klasse benutzerdefinierte Ereignishandler hinzufügen.  Mithilfe benutzerdefinierter Ereignisse können Sie Code hinzufügen, der ausgeführt wird, wenn ein Ereignishandler hinzugefügt oder entfernt wird bzw. wenn das Ereignis ausgelöst wird.  Der `AddHandler`\-Code für ein benutzerdefiniertes Ereignis wird allerdings nur ausgeführt, wenn Code zum Behandeln des Ereignisses von einem Benutzer hinzugefügt wird.  Berücksichtigen Sie beispielsweise, dass das `SampleExtension`\-Objekt im vorherigen Abschnitt ein `Load`\-Ereignis enthält, für das Sie einen benutzerdefinierten Ereignishandler hinzufügen sollten.  Das folgende Codebeispiel zeigt einen benutzerdefinierten Ereignishandler mit dem Namen `SampleExtensionLoad`, der beim Auftreten des `My.SampleExtension.Load`\-Ereignisses aufgerufen wird.  Wird Code zum Behandeln des neuen `My.SampleExtensionLoad`\-Ereignisses hinzugefügt, wird der `AddHandler`\-Teil dieses benutzerdefinierten Ereigniscodes ausgeführt.  Das Codebeispiel enthält die `MyApplication_SampleExtensionLoad`\-Methode, um ein Beispiel für einen Ereignishandler zu zeigen, der das `My.SampleExtensionLoad`\-Ereignis behandelt.  Beachten Sie, dass das `SampleExtensionLoad`\-Ereignis verfügbar ist, wenn Sie beim Bearbeiten der Datei ApplicationEvents.vb in der linken Dropdownliste oberhalb des Code\-Editors die Option **My Application Events** auswählen.  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> Entwurfsrichtlinien  
 Wenn Sie Erweiterungen für den `My`\-Namespace entwickeln, können Sie die Kosten für die Wartung der Erweiterungskomponenten mithilfe der folgenden Richtlinien minimieren.  
  
-   **Beziehen Sie nur die Erweiterungslogik ein.** Die in der Erweiterung des `My`\-Namespaces enthaltene Logik sollte nur den Code umfassen, der benötigt wird, um die erforderlichen Funktionen im `My`\-Namespace verfügbar zu machen.  Da Ihre Erweiterung in Benutzerprojekten als Quellcode enthalten ist, verursacht die Aktualisierung der Erweiterungskomponente hohe Pflegekosten und sollte nach Möglichkeit vermieden werden.  
  
-   **Minimieren Sie die Projektvoraussetzungen.** Wenn Sie Ihre Erweiterungen des `My`\-Namespaces erstellen, setzen Sie keine Verweise, Importe auf Projektebene oder spezielle Compilereinstellungen \(z. B. `Option Strict` deaktiviert\) voraus.  Minimieren Sie stattdessen Abhängigkeiten, und qualifizieren Sie durch das `Global`\-Schlüsselwort alle Typverweise vollständig.  Stellen Sie außerdem sicher, dass die Erweiterung mit aktivierter `Option Strict` kompiliert wird, um Fehler in der Erweiterung zu minimieren.  
  
-   **Isolieren Sie den Erweiterungscode.** Wenn Sie den Code in eine Datei einfügen, kann Ihre Erweiterung problemlos als Visual Studio\-Elementvorlage bereitgestellt werden.  Weitere Informationen finden Sie unter "Verpacken und Bereitstellen von Erweiterungen" weiter unten in diesem Thema.  Wenn Sie den gesamten Code der Erweiterung des `My`\-Namespaces in nur eine Datei oder in einen separaten Ordner in einem Projekt einfügen, fällt es den Benutzern zudem leichter, die Erweiterung des `My`\-Namespaces zu finden.  
  
##  <a name="designing"></a> Entwerfen von Klassenbibliotheken für My  
 Wie bei den meisten Objektmodellen funktionieren einige Entwurfsmuster gut im `My`\-Namespace, andere dagegen nicht.  Berücksichtigen Sie beim Entwerfen einer Erweiterung für den `My`\-Namespace die folgenden Prinzipien:  
  
-   **Zustandslose Methoden.** Methoden im `My`\-Namespace sollten eine vollständige Lösung für eine bestimmte Aufgabe bereitstellen.  Stellen Sie sicher, dass die Parameterwerte, die an die Methode übergeben werden, sämtliche Eingabewerte bereitstellen, die für die jeweilige Aufgabe benötigt werden.  Erstellen Sie keine Methoden, die auf einem vorherigen Zustand beruhen, z. B. auf geöffneten Verbindungen zu Ressourcen.  
  
-   **Globale Instanzen.** Der einzige Zustand, der im `My`\-Namespace beibehalten wird, gilt global für das Projekt.  Zum Beispiel kapselt `My.Application.Info` einen Zustand, der in der gesamten Anwendung verwendet wird.  
  
-   **Einfache Parametertypen.** Verwenden Sie keine komplexen Parametertypen.  Erstellen Sie stattdessen Methoden, die keine Parametereingaben erfordern oder die einfache Eingabetypen wie Zeichenfolgen, primitive Typen usw. verlangen.  
  
-   **Factorymethoden.** Bei einigen Typen ist die Erstellung von Instanzen notwendigerweise schwierig.  Wenn Sie Factorymethoden als Erweiterungen für den `My`\-Namespace bereitstellen, können Sie Typen, die unter diese Kategorie fallen, einfacher ermitteln und nutzen.  Ein Beispiel für eine gut funktionierende Factorymethode ist `My.Computer.FileSystem.OpenTextFileReader`.  In .NET Framework stehen mehrere Streamtypen zur Verfügung.  Wenn Sie Textdateien speziell angeben, hilft `OpenTextFileReader` dem Benutzer zu verstehen, welcher Stream verwendet werden soll.  
  
 Diese Richtlinien schließen allgemeine Entwurfsprinzipien für Klassenbibliotheken nicht aus.  Es handelt sich vielmehr um Empfehlungen, die für Entwickler optimiert sind, die Visual Basic und den `My`\-Namespace verwenden.  Allgemeine Entwurfsprinzipien zum Erstellen von Klassenbibliotheken finden Sie unter [Framework\-Entwurfsrichtlinien](../Topic/Framework%20Design%20Guidelines.md).  
  
##  <a name="packaging"></a> Verpacken und Bereitstellen von Erweiterungen  
 Sie können Erweiterungen des `My`\-Namespaces in eine Visual Studio\-Projektvorlage aufnehmen oder die Erweiterungen verpacken und als Visual Studio\-Elementvorlage bereitstellen.  Wenn Sie Ihre Erweiterungen des `My`\-Namespaces als Visual Studio\-Elementvorlage verpacken, können Sie die von Visual Basic bereitgestellten Fähigkeiten nutzen.  Aufgrund dieser Fähigkeiten können Sie eine Erweiterung einfügen, wenn ein Projekt auf eine bestimmte Assembly verweist. Außerdem können Benutzer Ihre Erweiterung des `My`\-Namespaces explizit mithilfe der Seite **My\-Erweiterungen** des Visual Basic\-Projekt\-Designers hinzufügen.  
  
 Ausführliche Informationen zum Bereitstellen von Erweiterungen des `My`\-Namespaces finden Sie unter [Packaging and Deploying Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## Siehe auch  
 [Packaging and Deploying Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)   
 [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [My\-Erweiterungen\-Seite im Projekt\-Designer](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)   
 [Seite "Anwendung", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)