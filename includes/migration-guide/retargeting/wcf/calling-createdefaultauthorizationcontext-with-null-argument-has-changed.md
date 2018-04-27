### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Das Aufrufen von CreateDefaultAuthorizationContext mit einem NULL-Argument wurde geändert

|   |   |
|---|---|
|Details|Die Implementierung des <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=name>-Elements, das von einem Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=name> mit dem NULL-Wert als Argument „authorizationPolicies“ zurückgegeben wurde, hat seine Implementierung in .NET Framework 4.6 geändert.|
|Vorschlag|In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor. In derartigen Fällen gibt es zwei Möglichkeiten, um das vorherige Verhalten wiederherzustellen:<ol><li>Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt. Verwenden Sie für mithilfe von IIS gehosteten Diensten das &lt;httpRuntime targetFramework=&quot;x.x&quot; /&gt;-Element, um Ihre Apps auf eine frühere Version von .NET Framework auszurichten.</li><li>Fügen Sie dem Abschnitt <code>&lt;appSettings&gt;</code> Ihrer Datei „app.config“ die folgende Zeile hinzu: <code>&lt;add key=&quot;appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext&quot; value=&quot;true&quot; /&gt;</code></li></ol>|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType></li></ul>|

