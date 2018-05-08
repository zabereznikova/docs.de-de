---
title: Dispose-Muster
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdcb746ae2d8c2262b0cd0c6c9dcaababb12bd63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dispose-pattern"></a>Dispose-Muster
Alle Programme abrufen eine oder mehrere Systemressourcen, z. B. Arbeitsspeicher, Systemhandles oder Datenbankverbindungen, im Rahmen ihrer Ausführung. Entwickler müssen solche Systemressourcen mit Vorsicht werden, da sie freigegeben werden müssen, nachdem sie eingerichtet und verwendet wurden.  
  
 Die CLR bietet Unterstützung für die automatische Speicherverwaltung. Verwalteter Speicher (mit dem c#-Operator zugeordnete Arbeitsspeicher `new`) muss nicht explizit freigegeben werden. Es wird automatisch vom Garbage Collector (GC) freigegeben. Dies müssen Entwickler von der Aufgabe aufwändig und schwer Freigeben von Arbeitsspeicher und wurde einer der Hauptgründe, warum die unvergleichlich hohe Produktivität von .NET Framework gewährt wurden.  
  
 Leider ist verwalteter Speicher nur eine verschiedener Arten von Systemressourcen. Ressourcen mit Ausnahme des verwalteten Speichers noch explizit freigegeben werden müssen und nicht verwalteten Ressourcen genannt werden. Der globale Katalogserver wurde ausdrücklich nicht entwickelt solche nicht verwalteten Ressourcen verwalten was bedeutet, dass die Verantwortung für die Verwaltung von nicht verwalteten Ressourcen in die Hände der Entwickler liegt.  
  
 Die CLR bietet Hilfe in nicht verwaltete Ressourcen freizugeben. <xref:System.Object?displayProperty=nameWithType> deklariert eine virtuelle Methode <xref:System.Object.Finalize%2A> (auch als "Finalizer" bezeichnet), wird vom GC aufgerufen, bevor der Speicher des Objekts vom GC freigegeben wird und überschrieben werden, kann um nicht verwaltete Ressourcen freizugeben. Typen, die den Finalizer außer Kraft setzen, werden als finalisierbaren Typen bezeichnet.  
  
 Obwohl Finalizer in einigen Szenarien Cleanup wirksam sind, haben sie zwei erhebliche Nachteile:  
  
-   Der Finalizer wird aufgerufen, wenn der globale Katalogserver erkennt, dass ein Objekt für die Auflistung geeignet sind. Dies erfolgt bei einigen unbestimmten Zeitraum nach die Ressource nicht mehr benötigt wird. Die Verzögerung zwischen den bei der Entwickler kann möchten oder Version der Ressource und die Uhrzeit, wann die Ressource tatsächlich von den Finalizer freigegeben wird, möglicherweise nicht akzeptabel in Programmen, die viele knappe Ressourcen (Ressourcen, die leicht erschöpft sein können) erwerben oder in Fällen, in denen Ressourcen kostspielige verwendet (z. B. große nicht verwalteten Speicherpuffer) beibehalten werden.  
  
-   Wenn die CLR einen Finalizer aufrufen muss, muss er Auflistung von Arbeitsspeicher für das Objekt verschieben, bis das nächste gerundet wird, der Garbagecollection (die Finalizer zwischen Auflistungen ausgeführt). Dies bedeutet, dass der Speicher des Objekts (und alle Objekte, denen er verweist) wird nicht für einen längeren Zeitraum freigegeben.  
  
 Aus diesem Grund der vertrauenden Seite ausschließlich auf Finalizer möglicherweise nicht geeignet, in vielen Szenarien, wenn es darauf ankommt, nicht verwaltete Ressourcen freizugeben so schnell wie möglich, beim Umgang mit knappe Ressourcen oder in äußerst leistungsfähigen Szenarien, in denen der hinzugefügten GC-Mehraufwand der Abschluss ist nicht zulässig.  
  
 Das Framework bietet die <xref:System.IDisposable?displayProperty=nameWithType> -Schnittstelle, die implementiert werden soll, um dem Entwickler stellen eine manuelle Möglichkeit, die nicht verwaltete Ressourcen freizugeben, sobald sie nicht benötigt werden. Sie bietet außerdem die <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> -Methode, die dem globalen Katalogserver, die erkennen kann ein Objekt wurde manuell verworfen und müssen nicht mehr freigegeben werden in diesem Fall kann der Speicher des Objekts früher freigegeben werden. Typen implementiert, die `IDisposable` Schnittstelle als Verwerfbare Typen bezeichnet.  
  
 Um die Verwendung und Implementierung der Finalizer zu standardisieren richtet sich an das Dispose-Muster und die `IDisposable` Schnittstelle.  
  
 Die wichtigsten Motivation für das Muster besteht darin Reduzierung der Komplexität der Implementierung von der <xref:System.Object.Finalize%2A> und <xref:System.IDisposable.Dispose%2A> Methoden. Die Komplexität ist die Tatsache, dass die Methoden einige, aber nicht alle Codepfade nutzen (die Unterschiede werden später in diesem Kapitel beschrieben). Darüber hinaus stehen aus Verlaufsgründen für die Benutzeroberflächenelemente des Musters im Zusammenhang mit der Entwicklung der sprachunterstützung für deterministische ressourcenverwaltung.  
  
 **Führen Sie ✓** das grundlegende Dispose-Muster für Typen, die Instanzen von Verwerfbare Typen implementieren. Finden Sie unter der [grundlegende Dispose-Muster](#basic_pattern) Abschnitt, um Details für das grundlegende Muster.  
  
 Wenn ein Typ für die Lebensdauer des anderen verwerfbare Objekte verantwortlich ist, benötigen Entwicklern eine Möglichkeit, diese zu verwerfen. Mithilfe des Containers `Dispose` Methode ist eine komfortable Methode, um dies zu ermöglichen.  
  
 **Führen Sie ✓** grundlegende Dispose-Muster implementiert wird und einen Finalizer bereitstellen, auf Ressourcen, die explizit freigegeben werden müssen und die keine Finalizer.  
  
 Beispielsweise sollte das Muster für Typen, die Speichern von nicht verwalteten Arbeitsspeicher implementiert werden. Die [finalisierbaren Typen](#finalizable_types) Abschnitt wird erläutert, Richtlinien, die im Zusammenhang mit der Finalizer zu implementieren.  
  
 **· ERWÄGEN SIE** die Implementierung des grundlegenden Dispose-Musters bei Klassen, die selbst keine verwalteten Ressourcen oder verwerfbaren Objekte enthalten, aber Untertypen umfassen können, die dies tun.  
  
 Ein hervorragendes Beispiel dafür ist die <xref:System.IO.Stream?displayProperty=nameWithType> -Klasse. Während es sich hierbei um eine abstrakte Basisklasse handelt, die keinerlei Ressourcen enthält, tun dies die meisten ihrer Unterklassen. Aus diesem Grund implementiert sie das Dispose-Muster.  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>Grundlegende Dispose-Muster  
 Die grundlegende Implementierung des Musters beinhaltet die Implementierung der `System.IDisposable` Schnittstelle und meldet die `Dispose(bool)` -Methode, die alle Ressourcen der Bereinigungslogik, gemeinsam genutzt werden die `Dispose` -Methode und der optionalen Finalizer.  
  
 Das folgende Beispiel zeigt eine einfache Implementierung der das grundlegende Muster:  
  
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
  
 Den booleschen Parameter `disposing` gibt an, ob die Methode aufgerufen wurde, aus der `IDisposable.Dispose` Implementierung oder von der Finalizer. Die `Dispose(bool)` Implementierung sollte überprüfen Sie den Parameter vor dem Zugriff auf andere Verweisobjekte (z. B. das Ressourcenfeld im vorhergehenden Beispiel). Solche Objekte nur zugegriffen werden soll, wenn die Methode aufgerufen wird, aus der `IDisposable.Dispose` Implementierung (bei der `disposing` Parameter gleich "true"). Wenn die Methode, von der Finalizer aufgerufen wird (`disposing` lautet "false"), andere Objekte nicht zugegriffen werden soll. Der Grund ist, dass Objekte in einem unvorhersehbaren Reihenfolge abgeschlossen werden und daher diese oder eine ihrer Abhängigkeiten möglicherweise bereits abgeschlossen.  
  
 In diesem Abschnitt gilt auch, Klassen, mit der eine Basis, die nicht bereits das Dispose-Muster implementiert wird. Wenn Sie von einer Klasse, die bereits das Steuerelementmuster implementiert erben, überschreiben Sie einfach die `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.  
  
 **Führen Sie ✓** deklarieren eine `protected virtual void Dispose(bool disposing)` Methode, um die gesamte Logik zu zentralisieren, die sich auf die Freigabe nicht verwalteter Ressourcen beziehen.  
  
 Bei dieser Methode sollten alle ressourcenbereinigung auftreten. Die Methode wird von beiden die Finalizer aufgerufen und die `IDisposable.Dispose` Methode. Der Parameter werden "false", wenn in einer Finalize-Methode aufgerufen. Es sollte verwendet werden, um sicherzustellen, dass jedem Code ausgeführt wird, während des Abschlusses nicht andere finalisierbare Objekte zugreift. Informationen zum Implementieren der Finalizer werden im nächsten Abschnitt beschrieben.  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **Führen Sie ✓** implementieren die `IDisposable` Schnittstelle durch den Aufruf einfach `Dispose(true)` gefolgt von `GC.SuppressFinalize(this)`.  
  
 Der Aufruf von `SuppressFinalize` sollte nur erfolgen, wenn `Dispose(true)` erfolgreich ausgeführt wird.  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X nicht** stellen die parameterlose `Dispose` virtuelle Methode.  
  
 Die `Dispose(bool)` Methode ist dasjenige, das von Unterklassen überschrieben werden sollte.  
  
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
  
 **X nicht** alle Überladungen der deklarieren die `Dispose` andere Methode als `Dispose()` und `Dispose(bool)`.  
  
 `Dispose` Berücksichtigen Sie ein reserviertes Wort zu helfen, dieses Muster Sicherungssystems und schließt Verwechslungen zwischen Implementierer, Benutzer und -Compiler. Für einige Sprachen empfiehlt sich, dieses Muster für bestimmte Typen automatisch zu implementieren.  
  
 **Führen Sie ✓** ermöglichen die `Dispose(bool)` Methode, die mehr als einmal aufgerufen werden. Die Methode empfiehlt sich, nach dem ersten Aufruf nichts zu tun.  
  
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
  
 **X vermeiden** Auslösen einer Ausnahme heraus `Dispose(bool)` außer in kritischen Situationen, in denen der enthaltende Prozess wurde beschädigt (Speicherverlusten, inkonsistent Freigabezustand usw..).  
  
 Benutzer erwarten, dass ein Aufruf von `Dispose` wird keine Ausnahme ausgelöst.  
  
 Wenn `Dispose` konnte eine Ausnahme ausgelöst werden, weitere finally-Block Bereinigungslogik wird nicht ausgeführt. Um dieses Problem umgehen, muss der Benutzer zum Umschließen von jedem Aufruf von `Dispose` (innerhalb der finally-block!) in einem Try-Block, der in sehr komplexen Bereinigung Handler führt. Wenn die Ausführung einer `Dispose(bool disposing)` Methode nie löst eine Ausnahme aus, wenn der disposing "false" ist. Auf diese Weise wird der Prozess beendet, wenn in einem Finalizer-Kontext ausgeführt.  
  
 **✓ FÜHREN** Auslösen einer <xref:System.ObjectDisposedException> über ein Element, das verwendet werden kann, nachdem das Objekt verworfen wurde.  
  
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
  
 **✓ GGF.** als Methode `Close()`, zusätzlich zu den `Dispose()`, wenn schließen standard Terminologie im Bereich ist.  
  
 Dabei ist es wichtig, dass Sie stellen der `Close` Implementierung identisch mit `Dispose` und implementieren Sie die `IDisposable.Dispose` Methode explizit.  
  
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
## <a name="finalizable-types"></a>Finalisierbaren Typen  
 Finalisierbare Typen sind Typen, die das grundlegende Dispose-Muster zu erweitern, indem Sie den Finalizer überschreiben und das Bereitstellen von Codepfad in seiner Finalisierung verfolgt die `Dispose(bool)` Methode.  
  
 Finalizer sind bekanntermaßen schwierig zu ordnungsgemäß implementieren, in erster Linie verwendet werden, da Sie während ihrer Ausführung bestimmter (normalerweise gültigen) Annahmen über den Zustand des Systems vornehmen können. Die folgenden Richtlinien sollten eine sorgfältige berücksichtigt werden.  
  
 Beachten Sie, dass einige der Richtlinien angewendet werden nicht nur auf die `Finalize` -Methode, jedoch keinen Code von einem Finalizer aufgerufen. Bei der grundlegende Dispose-Muster zuvor definiert, bedeutet das Logik, die in ausgeführt wird `Dispose(bool disposing)` bei der `disposing` Parameter ist "false".  
  
 Wenn die Basisklasse bereits finalisierbaren und die grundlegende Dispose-Muster implementiert, sollten Sie nicht überschreiben `Finalize` erneut aus. Sie sollten stattdessen nur überschreiben die `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.  
  
 Der folgende Code zeigt ein Beispiel eines finalisierbaren Typs:  
  
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
  
 **X vermeiden** Typen finalisierbaren vornehmen.  
  
 Bedenken Sie sorgfältig die jeder Fall, in dem Sie vorstellen, dass ein Finalizer erforderlich ist. Es gibt ein echten Kosten Instanzen mit Finalizer aus Sicht der Komplexität einer Leistung und den Code. Es vorziehen, z. B. mit der Ressource Wrapper <xref:System.Runtime.InteropServices.SafeHandle> um nicht verwaltete Ressourcen möglichst zu kapseln, in diesem Fall ein Finalizer wird nicht erforderlich, da der Wrapper für einen eigenen ressourcenbereinigung zuständig ist.  
  
 **X nicht** Werttypen finalisierbaren vornehmen.  
  
 Nur Verweistypen abrufen tatsächlich von der CLR freigegeben und daher wird jeder Versuch, platzieren Sie einen Finalizer für einen Werttyp wird ignoriert. Die C#- und C++-Compiler erzwingen diese Regel.  
  
 **Führen Sie ✓** stellen einen Typ finalisierbaren, wenn der Typ verantwortlich ist für eine nicht verwaltete Ressource, die über keinen eigenen Finalizer freigeben.  
  
 Wenn Sie den Finalizer zu implementieren, rufen Sie einfach `Dispose(false)` und fügen Sie alle Ressourcen Bereinigungslogik innerhalb der `Dispose(bool disposing)` Methode.  
  
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
  
 **Führen Sie ✓** das grundlegende Dispose-Muster für jede finalisierbaren Typ zu implementieren.  
  
 Dadurch kann Benutzer des Typs eine deterministische Bereinigung von gleichen Ressourcen explizit führen Sie für die der Finalizer verantwortlich ist.  
  
 **X nicht** finalisierbare Objekte in der Finalizer-Codepfad zugegriffen werden, da ist es bedeutendes Risiko, dass sie bereits finalisiert sein werden.  
  
 Angenommen, ein abzuschließendes Objekt ein, die einen Verweis auf eine andere abzuschließendes Objekt B enthält zuverlässig können keine B in die Finalize-Methode oder umgekehrt. Finalizer werden in zufälliger Reihenfolge (nicht genügend eine schwache Sortierung Garantie für Handleressourcen) aufgerufen.  
  
 Bedenken Sie außerdem, dass in statischen Variablen gespeicherten Objekte an bestimmten Punkten während der Anwendung Domäne entladen oder beim Beenden des Prozesses erfasst abrufen. Zugreifen auf eine statische Variable, die bezieht sich auf ein abzuschließendes Objekt (oder Aufrufs einer statischen Methode, die in statischen Variablen gespeicherten Werte verwenden kann) möglicherweise nicht sichere If <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> "Wahr" zurückgegeben.  
  
 **Führen Sie ✓** stellen Ihre `Finalize` geschützte Methode.  
  
 C#, C++ und VB.NET Entwickler benötigen keine hierzu kümmern, da der Compiler helfen, um diese Richtlinie zu erzwingen.  
  
 **X nicht** können Ausnahmen Escapezeichen aus der Finalizer-Logik, mit Ausnahme von System kritische Fehler.  
  
 Wenn von einem Finalizer eine Ausnahme ausgelöst wird, wird die CLR heruntergefahren, nach den gesamten Prozess (ab .NET Framework, Version 2.0), verhindern, dass andere Finalizer ausführen und die Ressourcen aus, die kontrolliert freigegeben wird.  
  
 **✓ GGF.** erstellen und verwenden ein abzuschließendes Objekt inaktiv kritische (ein Typ mit einer Typhierarchie, die enthält <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) für Situationen, in der ein Finalizer absolut werden auch bei der erzwungenen Anwendung Domäne entladen und Threads ausgeführt muss, Bricht ab.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
