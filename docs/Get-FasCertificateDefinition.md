# Get-FasCertificateDefinition

## Synopsis
View existing Certificate Definition objects (recipe for issuing a certificate).

## Syntax

```
Get-FasCertificateDefinition [-Name <String>] [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
View the configuration of existing Certificate Definition objects that the FAS is using to generate user certificates.

When generating a certificate, FAS requires various pieces of information. 
Including:
    - The CertificateTemplate to request (see Get-FasMsTemplate)
    - A list of loadbalanced/failover Certificate Authority Addresses (see Get-FasMsCertificateAuthority)
    - The ID of the AuthorizationCertificate to use to Authorize the request (see Get-FasAuthorizationCertificate)
    - A list of additional Issuance Policy OIDs to add to the certificate request (see Get-FasPolicyOid)
    - A flag indicating if the certificate can be used as an in-session Virtual Smart Card, or only for the logon process.

Note that Certificate Definition objects can only be created and managed by the FAS Server administrator, although they can be referenced by "Rule" administrators.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Get-FasCertificateDefinition
```

Description

-----------

Lists the Certificate Definition objects configured on the FAS Server

## Parameters

### -Name
Specify the name of the Certificate Definition to view.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Address
Address of FAS Server (or $NULL to use $CitrixFasAddress)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $CitrixFasAddress
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
User name to use for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Password for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns a list of certificate definitions

## Notes

## Related Links

[New-FasCertificateDefinition]()

[Set-FasCertificateDefinition]()

[Remove-FasCertificateDefinition]()


