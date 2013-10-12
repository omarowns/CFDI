# CFDI para principiantes en CFDI

El sistema de generación y sellado de facturas es una patada en los genitales. Este gem pretende ser una bolsa de hielos. Igual va a doler, pero espero que al menos no quede moretón.

## Instalación

    gem install cfdi

## Uso

Puedes ver [crear_factura.rb](examples/crear_factura.rb) para darse una mejor idea, pero acá va un resumen:

    require 'cfdi'
	factura = CFDI::Comprobante.new
	
	emisor = {
		rfc: 'un RFC',
		nombre: 'una razón social o nombre',
		domicilioFiscal: CFDI::Domicilio.new
		expedidoEn: CFDI::Domicilio.new
		regimenFiscal: 'general'
	}
	
	# lo mismo para el receptor
	
	# porque XML! ES LO DE HOY! BIENVENIDOS A 2001!
	puts factura.to_xml
	
	# O talvez evolucionamos a un formato de intercambio de datos menos castroso
	require 'json'
	puts JSON.pretty_generate(factura.to_h)
	
## Licencia

![What the fuck Public License](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)

Como es costumbre, todo bajo WTFPL. La licencia completa la puedes leer acá: [Licencia](LICENSE.txt)