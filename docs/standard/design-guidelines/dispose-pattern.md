---
title: "Dispose-Muster | Microsoft Docs"
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
  - "Dispose-Methode"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Dispose-Methode"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Finalize-Methode"
  - "Anpassen des Namens der Dispose-Methode"
  - "Finalize-Methode"
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Dispose-Muster
Alle Programme erhalten eine oder mehrere Systemressourcen, z. B. Arbeitsspeicher, Systemhandles oder Datenbankverbindungen, im Rahmen ihrer Ausführung. Entwickler müssen vorsichtig, wenn Sie eine solche Systemressourcen verwendet werden, da sie freigegeben werden müssen, nachdem sie abgerufen und verwendet wurden.  
  
 Die CLR bietet Unterstützung für die automatische Verwaltung. Verwalteter Speicher \(Arbeitsspeicher, die mit dem C\#\-Operator zugewiesen `new`\) muss nicht explizit freigegeben werden. Es wird automatisch vom Garbage Collector \(GC\) freigegeben. Dies müssen Entwickler von der Aufgabe mühsam und schwierig Freigeben von Arbeitsspeicher und die wichtigsten Gründe für die beispiellosen Produktivität von .NET Framework geboten wurde.  
  
 Leider ist nur eine von vielen Arten von Systemressourcen, verwalteter Speicher. Ressourcen mit Ausnahme des verwalteten Speichers immer noch explizit freigegeben werden müssen und als nicht verwaltete Ressourcen bezeichnet. Die GC wurde speziell nicht entwickelt, eine solche nicht verwalteten Ressourcen verwalten, was bedeutet, dass die Verantwortung für die Verwaltung von nicht verwalteten Ressourcen in die Hände der Entwickler liegt.  
  
 Die CLR bietet Hilfe in verwaltete Ressourcen freizugeben.<xref:System.Object?displayProperty=fullName> deklariert eine virtuelle Methode <xref:System.Object.Finalize%2A> \(auch den Finalizer genannt\), wird vom Garbage Collector aufgerufen, bevor der Speicher des Objekts durch die Garbage Collection wieder zugänglich gemacht wird, und überschrieben werden, kann um nicht verwaltete Ressourcen freizugeben. Typen, die den Finalizer überschreiben werden beendbare Typen genannt.  
  
 Obwohl Finalizer in einigen Szenarien Cleanup wirksam sind, verfügen sie über zwei bedeutende Nachteile:  
  
-   Der Finalizer wird aufgerufen, wenn die GC erkennt, dass ein Objekt für die Auflistung. Dies erfolgt bei einigen unbestimmten Zeitraum nach der Ressource nicht mehr benötigt wird. Die Verzögerung bei der Entwickler konnten, oder möchten Version der Ressource und die Uhrzeit, wann die Ressource tatsächlich vom Finalizer freigegeben wird, möglicherweise nicht akzeptabel in Programmen, die viele knappe Ressourcen \(die Ressourcen, die einfach erschöpft sein können\) oder in Fällen, in denen Ressourcen teuer zu verwenden \(z. B. großen nicht verwalteten Speicherpuffer\) sind.  
  
-   Wenn die CLR einen Finalizer aufrufen muss, muss es Auflistung von der Speicher des Objekts verschieben, bis die nächste Garbage collection \(die Finalizer zwischen Sammlungen\) runden. Dies bedeutet, dass der Speicher des Objekts \(und alle Objekte, auf die verwiesen\) wird nicht für einen längeren Zeitraum freigegeben.  
  
 Aus diesem Grund kann ausschließlich auf Finalizer nicht angemessen sein in vielen Szenarien ist es wichtig, nicht verwaltete Ressourcen freizugeben so schnell wie möglich, beim Umgang mit knappe Ressourcen oder hoch leistungsfähigen Szenarien in denen hinzugefügten GC Aufwand der Beendigung nicht akzeptabel ist.  
  
 Das Framework bietet die <xref:System.IDisposable?displayProperty=fullName> \-Schnittstelle, die implementiert werden soll, um dem Entwickler die Möglichkeit manuelle, nicht verwaltete Ressourcen freizugeben, sobald sie nicht benötigt werden. Es enthält auch die <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> \-Methode, die der GC, mitteilen, kann ein Objekt wurde manuell wieder entfernt, und muss nicht mehr abgeschlossen werden, in diesem Fall kann der Speicher des Objekts früher freigegeben werden. Typen, implementieren die `IDisposable` Schnittstelle als Verwerfbare Typen bezeichnet.  
  
 Das Dispose\-Muster soll die Verwendung und Implementierung von Finalizern standardisieren und die `IDisposable` Schnittstelle.  
  
 Der Hauptgrund für das Muster reduziert die Komplexität der Implementierung ist die <xref:System.Object.Finalize%2A> und <xref:System.IDisposable.Dispose%2A> Methoden. Die Komplexität ist dadurch bedingt, dass die Methoden einige, aber nicht alle Codepfade Teilen \(die Unterschiede werden später in diesem Kapitel beschrieben\). Es gibt außerdem Verlaufsdaten Gründe für einige Elemente des Musters im Zusammenhang mit der Entwicklung der Language\-Unterstützung zur Verwaltung von Ressourcen deterministisch.  
  
 **✓ führen** der grundlegende Dispose\-Muster für Typen, die Instanzen von verwerfbaren Typen implementieren. Finden Sie unter der [grundlegende Dispose\-Muster](#basic_pattern) Abschnitt ausführliche Informationen über das grundlegende Muster.  
  
 Wenn ein Typ für die Lebensdauer des anderen verwerfbare Objekte verantwortlich ist, benötigen Entwickler eine Möglichkeit, diese zu verwerfen. Mithilfe des Containers `Dispose` Methode ist eine einfache Möglichkeit, dies zu ermöglichen.  
  
 **✓ führen** der grundlegende Dispose\-Muster zu implementieren und einen Finalizer bereitstellen, auf Ressourcen, die explizit freigegeben werden müssen und die keine Finalizer.  
  
 Beispielsweise sollte das Muster für Typen, die Speichern von nicht verwalteten Arbeitsspeicher implementiert werden. Die [beendbare Typen](#finalizable_types) Abschnitt werden Richtlinien vorgestellt, die im Zusammenhang mit der Implementierung von Finalizern.  
  
 **✓ ggf.** für Klassen, selbst enthalten, nicht verwalteten Ressourcen oder verwerfbare Objekte sind jedoch wahrscheinlich Untertypen, die das grundlegende Dispose\-Muster implementieren.  
  
 Ein hervorragendes Beispiel hierfür ist die <xref:System.IO.Stream?displayProperty=fullName> Klasse. Obwohl es sich um eine abstrakte Basisklasse, die Ressourcen enthalten ist, nicht, die meisten ihrer Unterklassen, und aus diesem Grund dieses Muster implementiert.  
  
<a name="basic_pattern"></a>   
## Grundlegende Dispose\-Muster  
 Die grundlegende Implementierung des Musters umfasst die Implementierung der `System.IDisposable` \-Schnittstelle und deklarieren die `Dispose(bool)` Methode für das Implementieren der Bereinigungslogik für alle Ressourcen gemeinsam genutzt werden die `Dispose` \-Methode und der optionalen Finalizer.  
  
 Das folgende Beispiel zeigt eine einfache Implementierung von das grundlegende Muster:  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder(){  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        if (disposing){  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 Der boolesche Parameter `disposing` Gibt an, ob die Methode aufgerufen wurde, aus der `IDisposable.Dispose` Implementierung oder vom Finalizer. Die `Dispose(bool)` Implementierung sollten die Parameter überprüfen, bevor Sie den Zugriff auf andere Reference\-Objekte \(z. B. das Ressourcenfeld im vorhergehenden Beispiel\). Solche Objekte sollte nur zugegriffen werden, wenn die Methode aufgerufen wird die `IDisposable.Dispose` Implementierung \(wenn der `disposing` \-Parameter gleich True ist\). Wenn die Methode von der Finalizer aufgerufen wird \(`disposing` ist "false"\), andere Objekte sollten nicht zugegriffen werden. Der Grund ist, dass Objekte in einem unvorhersehbaren Auftrag abgeschlossen sind und daher diese oder eine ihrer Abhängigkeiten möglicherweise bereits abgeschlossen.  
  
 Dieser Abschnitt gilt auch Klassen mit einer Datenbank, die nicht bereits das Dispose\-Muster implementiert wird. Wenn Sie von einer Klasse erben, die Muster bereits implementiert, überschreiben Sie einfach die `Dispose(bool)` Methode zum Bereitstellen zusätzlicher Ressourcen Bereinigungslogik.  
  
 **✓ führen** deklarieren Sie eine geschützte virtuelle Void `Dispose(bool disposing)` Methode, um die gesamte Logik zu zentralisieren beziehen, nicht verwaltete Ressourcen frei.  
  
 In dieser Methode sollte alle Bereinigung von Ressourcen auftreten. Die Methode wird vom beide Finalizer aufgerufen und die `IDisposable.Dispose` Methode. Der Parameter werden false, wenn in einem Finalizer aufgerufen. Es sollte verwendet werden, um sicherzustellen, dass jeder Code ausgeführt wird, während des Abschlusses keine andere finalisierbare Objekte zugreift. Details der Implementierung von Finalizern werden im nächsten Abschnitt beschrieben.  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ führen** implementieren die `IDisposable` Schnittstelle einfach aufrufen `Dispose(true)` gefolgt von `GC.SuppressFinalize(this)`.  
  
 Der Aufruf von `SuppressFinalize` sollte nur erfolgen, wenn `Dispose(true)` erfolgreich ausgeführt wird.  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X nicht** stellen die parameterlose `Dispose` virtuelle Methode.  
  
 Die `Dispose(bool)` Methode ist diejenige, die von Unterklassen überschrieben werden sollen.  
  
```  
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
```  
  
 **X nicht** deklarieren alle Überladungen der `Dispose` andere Methode als `Dispose()` und `Dispose(bool)`.  
  
 `Dispose` Berücksichtigen Sie dieses Muster festzuschreiben und Verwirrung unter Implementierer, Benutzer und Compiler zu verhindern, dass ein reserviertes Wort. In einigen Sprachen können dieses Muster automatisch auf bestimmte Typen implementieren.  
  
 **✓ führen** ermöglichen die `Dispose(bool)` \-Methode mehr als einmal aufgerufen wird. Die Methode möglicherweise nach dem ersten Aufruf nichts auswählen.  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **X vermeiden** Auslösen einer Ausnahme innerhalb von `Dispose(bool)` außer in kritischen Situationen, in denen der enthaltende Prozess wurde beschädigt \(Speicherverlusten, freigegebenen inkonsistent usw..\).  
  
 Benutzer erwarten, dass ein Aufruf von `Dispose` wird keine Ausnahme ausgelöst wird.  
  
 Wenn `Dispose` eine Ausnahme auslösen könnte, weitere Bereinigungslogik der finally\-Block wird nicht ausgeführt. Dieses Problem, zu umgehen die Benutzer müsste jeder Aufruf umschließen `Dispose` \(innerhalb der finally\-block\!\) in einem Try\-Block zu sehr komplexen Bereinigung Handler führt. Ausführen einer `Dispose(bool disposing)` Methode nie löst eine Ausnahme aus, wenn der disposing "false" ist. Auf diese Weise wird den Prozess beendet, Ausführung innerhalb einer Finalizer\-Kontext.  
  
 **✓ führen** löst ein <xref:System.ObjectDisposedException> aus jedem Element, das verwendet werden kann, nachdem das Objekt freigegeben wurde.  
  
```  
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething(){  
           if(disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
            ...  
    }  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓ ggf.** Methode bereitgestellt `Close()`, zusätzlich zu den `Dispose()`, wenn schließen standard\-Terminologie im Bereich ist.  
  
 Dabei ist es wichtig, dass Sie machen die `Close` Implementierung identisch mit `Dispose` und implementieren Sie die `IDisposable.Dispose` Methode explizit.  
  
```  
public class Stream : IDisposable {  
    IDisposable.Dispose(){  
        Close();  
    }  
    public void Close(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## Beendbare Typen  
 Beendbare Typen sind Typen, die das grundlegende Dispose\-Muster zu erweitern, indem Überschreiben des Finalizers und Beendigungscodepfad in die `Dispose(bool)` Methode.  
  
 Finalizer sind bekanntermaßen schwierig zu ordnungsgemäß implementieren, hauptsächlich, da Sie während der Ausführung bestimmter \(normalerweise gültigen\) Annahmen über den Zustand des Systems vornehmen können. Die folgenden Richtlinien sollten sorgfältig berücksichtigt werden.  
  
 Beachten Sie, dass einige der Richtlinien, die nicht nur auf gelten die `Finalize` \-Methode, aber für den gesamten Code von einem Finalizer aufgerufen. Bei der grundlegende Dispose\-Muster zuvor definierten Logik zur innerhalb bedeutet `Dispose(bool disposing)` bei der `disposing` Parameter ist "false".  
  
 Wenn die Basisklasse bereits finalisierbaren und die grundlegende Dispose\-Muster implementiert, sollten Sie nicht überschreiben `Finalize` erneut. Sie sollten stattdessen einfach überschreiben die `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.  
  
 Der folgende Code zeigt ein Beispiel für eine beendbare:  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder(){  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing){  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing){ // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **X vermeiden** Typen beendbare vornehmen.  
  
 Überlegen Sie jeder Fall, in dem Sie denken, dass es sich bei ein Finalizer erforderlich ist. Es ist eine echte Kosten im Zusammenhang mit Instanzen mit Finalizer aus Sicht für eine Leistung und den Code Komplexität. Lieber mit einem Wrapper Ressource wie <xref:System.Runtime.InteropServices.SafeHandle> um nicht verwaltete Ressourcen möglichst kapseln, in diesem Fall ein Finalizer wird nicht erforderlich, da der Wrapper für die Bereinigung seiner eigenen Ressourcen zuständig ist.  
  
 **X nicht** Werttypen beendbare vornehmen.  
  
 Nur Verweistypen abrufen tatsächlich von der CLR beendet, und somit jeder Versuch, einen Finalizer für einen Werttyp platzieren ignoriert werden. Die C\#\- und C\+\+\-Compiler erzwingen diese Regel.  
  
 **✓ führen** stellen ein abzuschließendes, wenn der Typ verantwortlich ist für eine nicht verwaltete Ressource, die einen eigenen Finalizer nicht freigeben.  
  
 Wenn den Finalizer zu implementieren, rufen Sie einfach `Dispose(false)` und fügen Sie alle Ressourcen Bereinigungslogik innerhalb der `Dispose(bool disposing)` Methode.  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        ...  
    }  
}  
```  
  
 **✓ führen** auf jedem beendbare das grundlegende Dispose\-Muster zu implementieren.  
  
 Dadurch kann Benutzer des Typs eine deterministische Bereinigung von diese Ressourcen explizit auszuführen, für die der Finalizer zuständig ist.  
  
 **X nicht** zugreifen, um finalisierbare Objekte in der Pfad für den Finalizer, da bedeutendes Risiko, dass sie bereits finalisiert sein werden.  
  
 Beispielsweise ein abzuschließendes Objekt ein, die einen Verweis auf ein anderes abzuschließendes Objekt B kann nicht zuverlässig verwenden B in die Finalize\-Methode oder umgekehrt. Finalizer werden in zufälliger Reihenfolge \(kleiner als eine schwache Sortierung Garantie für kritische Finalisierung\) aufgerufen.  
  
 Achten Sie zudem, dass Objekte in statischen Variablen gespeichert an bestimmten Punkten während der Anwendung Domäne entladen oder beim Beenden des Prozesses erfasst abrufen. Zugreifen auf eine statische Variable, das auf ein abzuschließendes Objekt inaktiv \(oder einen Aufruf einer statischen Methode, die in statischen Variablen gespeicherten Werte verwenden kann\) ist möglicherweise nicht sichere If <xref:System.Environment.HasShutdownStarted%2A?displayProperty=fullName> Gibt true zurück.  
  
 **✓ führen** stellen Ihre `Finalize` geschützte Methode.  
  
 C\#, C\+\+ und VB.NET Entwickler brauchen, Gedanken Compiler sind hilfreich, um diese Richtlinie zu erzwingen.  
  
 **X nicht** können Ausnahmen Escapezeichen aus der Finalizer\-Logik, mit Ausnahme von System kritische Fehler.  
  
 Wenn von einem Finalizer eine Ausnahme ausgelöst wird, wird die CLR den gesamten Prozess \(ab .NET Framework Version 2.0\), beendet verhindert, dass andere Finalizer ausgeführt und die Ressourcen aus auf kontrollierte Weise freigegeben wird.  
  
 **✓ ggf.** erstellen und Verwenden eines kritischen abzuschließendes Objekts \(ein Typ mit einer Typhierarchie, die enthält <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>\) für Situationen, in der ein Finalizer absolut werden auch bei Ausfällen erzwungenen Anwendungsdomäne ausgeführt muss, entladen und Threadabbrüche.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)   
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)