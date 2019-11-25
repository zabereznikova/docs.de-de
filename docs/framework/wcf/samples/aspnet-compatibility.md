---
title: ASP.NET-Kompatibilität
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: af03b16081f0e33764d3ef83519f6e50e6b97152
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141795"
---
# <a name="aspnet-compatibility"></a>ASP.NET-Kompatibilität

In diesem Beispiel wird veranschaulicht, wie der ASP.NET-Kompatibilitätsmodus in Windows Communication Foundation (WCF) aktiviert wird. Dienste, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden, sind vollständig in der ASP.NET-Anwendungs Pipeline und können ASP.NET-Funktionen wie die Datei-/URL-Autorisierung, den Sitzungs Status und die <xref:System.Web.HttpContext>-Klasse nutzen. Die <xref:System.Web.HttpContext>-Klasse ermöglicht den Zugriff auf Cookies, Sitzungen und andere ASP.NET-Funktionen. Dieser Modus erfordert, dass die Bindungen den HTTP-Transport verwenden und der Dienst selbst in IIS gehostet ist.

In diesem Beispiel ist der Client eine Konsolenanwendung (eine ausführbare Datei), und der Dienst wird in Internetinformationsdiensten (IIS) gehostet.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Für dieses Beispiel ist ein .NET Framework 4-Anwendungs Pool erforderlich, um ausgeführt werden zu können. Führen Sie die folgenden Schritte aus, um einen neuen Anwendungspool zu erstellen oder den Standardanwendungspool zu ändern.

1. Öffnen Sie die **Systemsteuerung**.  Öffnen Sie das Applet " **Verwaltung** " unter der Überschrift " **System und Sicherheit** ". Öffnen Sie das Applet **Internetinformationsdienste (IIS)-Manager** .

2. Erweitern Sie im Bereich **Verbindungen** den Eintrag TreeView. Wählen Sie den Knoten **Anwendungs Pools** aus.

3. Klicken Sie mit der rechten Maustaste auf das Listenelement **DefaultAppPool** , und wählen Sie **Grundeinstellungen...** aus, um den Standard Anwendungs Pool für die Verwendung von .NET Framework 4 festzulegen (was zu Inkompatibilitäts Problemen bei vorhandenen Websites führen kann). Legen Sie den pulldowndown der **.NET Framework-Version** auf **.NET Framework v 4.0.30128** (oder höher) fest.

4. Um einen neuen Anwendungs Pool zu erstellen, der .NET Framework 4 verwendet (um die Kompatibilität für andere Anwendungen beizubehalten), klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungs Pools** , und wählen Sie **Anwendungs Pool hinzufügen**aus. Benennen Sie den neuen Anwendungs Pool, und legen Sie den pulldowndownvorgang der **.NET Framework-Version** auf **.NET Framework v 4.0.30128** (oder höher) fest. Nachdem Sie die Schritte unten ausgeführt haben, klicken Sie mit der rechten Maustaste auf die Anwendung **Service Model Samples** , und wählen Sie **Anwendung verwalten**, **Erweiterte Einstellungen...** aus. Legen Sie den **Anwendungs Pool** auf den neuen Anwendungs Pool fest.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

Dieses Beispiel basiert auf den ersten Schritten, durch die ein Rechner Dienst [implementiert wird.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Der `ICalculator`-Vertrag wurde als `ICalculatorSession`-Vertrag geändert, damit eine Reihe von Vorgängen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculatorSession
{
    [OperationContract]
    void Clear();
    [OperationContract]
    void AddTo(double n);
    [OperationContract]
    void SubtractFrom(double n);
    [OperationContract]
    void MultiplyBy(double n);
    [OperationContract]
    void DivideBy(double n);
    [OperationContract]
    double Result();
}
```

Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst mithilfe der Funktion den Status für jeden Client bei. Der Client kann das aktuelle Ergebnis abrufen, indem er `Result` aufruft, und es auf null löschen, indem er `Clear` aufruft.

Der Dienst verwendet die ASP.NET-Sitzung, um das Ergebnis für jede Client Sitzung zu speichern. Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jeden Client über mehrere Aufrufe des Diensts hinweg beizubehalten.

> [!NOTE]
> ASP.NET-Sitzungs Status und WCF-Sitzungen sind sehr unterschiedliche Dinge. Weitere Informationen zu WCF-Sitzungen finden Sie in der [Sitzung](../../../../docs/framework/wcf/samples/session.md) .

Der Dienst hat eine intime Abhängigkeit vom ASP.NET-Sitzungszustand und erfordert den ASP.NET-Kompatibilitätsmodus, um ordnungsgemäß zu funktionieren. Diese Anforderungen werden deklarativ durch die Übernahme des `AspNetCompatibilityRequirements`-Attributs ausgedrückt.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode =
                       AspNetCompatibilityRequirementsMode.Required)]
public class CalculatorService : ICalculatorSession
{
    double Result
    {  // store result in AspNet Session
       get {
          if (HttpContext.Current.Session["Result"] != null)
             return (double)HttpContext.Current.Session["Result"];
          return 0.0D;
       }
       set
       {
          HttpContext.Current.Session["Result"] = value;
       }
    }
    public void Clear()
    {
        Result = 0.0D;
    }
    public void AddTo(double n)
    {
        Result += n;
    }
    public void SubtractFrom(double n)
    {
        Result -= n;
    }
    public void MultiplyBy(double n)
    {
        Result *= n;
    }
    public void DivideBy(double n)
    {
        Result /= n;
    }
    public double Result()
    {
        return Result;
    }
}
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

3. Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup. bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten. Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.

4. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="see-also"></a>Siehe auch

- [AppFabric-Hosting-und persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
