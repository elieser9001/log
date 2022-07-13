<img src="https://raw.githubusercontent.com/elieser9001/assets/main/antenna.png"
     alt="windows_icon"
     style="float: left; margin-right: 10px;" />
# NetSuites

En la universidad en 1999 hice un sistema usando Sockets para administrar remotamente todas las estaciones de Windows NT en los laboratorios de informática para llevar el control del tiempo de uso de cada una de las estaciones (en su tiempo era como un sistema que hoy en día es usado para administrar los cibercafes) entre las funciones que le integre estaba la de vigilar por medio de las Windows Api (Winapi) cualquier palabra prohibida como por ejemplo: pornografía, apuestas y demás palabras claves restringidas en el uso académico dentro de los títulos de las ventanas abiertas y proceder a cerrarlas y notificar al supervisor del suceso acontecido.

Use Visual Basic 5 y luego lo actualice a la versión 6 con Sockets usando protocolos TCP y UDP para el broadcast que me permitía agregar las direcciones IP's de todas las estaciones que tenían instalado mi sistema servidor y así se muestran automáticamente en el sistema cliente, por lo cual termine desarrollando 2 sistemas, un cliente y un servidor.

Las fotos a continuación son tomadas de una copia hecha hace más de 2 décadas a la tesis original.

<center>
<img src="https://github.com/elieser9001/assets/blob/main/netsuite1.jpeg?raw=true"
     alt="netsuite"
     style="width: 400px" />
</center>

<center>
<img src="https://github.com/elieser9001/assets/blob/main/netsuite2.jpeg?raw=true"
     alt="netsuite"
     style="width: 400px" />
</center>

<center>
<img src="https://github.com/elieser9001/assets/blob/main/netsuite3.jpeg?raw=true"
     alt="netsuite"
     style="width: 400px" />
</center>


___

<img src="https://github.com/elieser9001/assets/blob/main/netjoe1.png?raw=true"
     alt="netjoe"
     style="float: left; margin-right: 10px;" />

# NetJoe

A comienzos de la primera década del 2000, hice en Delphi 6, un troyano llamado NetJoe, me inspiré en el Netbus. Ver como funcionaba el Netbus en la época de los 90's para mí fue ver magia pura, por eso decidí que algún día iba a hacer uno propio y el resultado fue el NetJoe, en las noches solía escanear el puerto 12345 del rango de mi IP y encontrar computadoras que tenían el servidor de Netbus activo y así poder entonces comunicarme con esos usuarios para hablar con ellos, porque yo infería que si lo tenían activo es porque le interesaba tanto la programación como a mí y poder contarle que estaba haciendo uno con más funciones que el Netbus, luego los agregaba a mi Msn Messenger y desde ahí hablabamos mejor. Llegué a vender por Mercadolibre alrededor de 3 copias, donde lo usaba para darle soporte a los que me lo compraban.

Recuerdo que también hice una versión de NetJoe para usar conexión reversa.

Las funciones que le hice en cada Tab:

**Informacion:**
- Nombre del host remoto.
- Ruta de la carpeta del Sistema remoto.
- Usuario logeado remoto.

**Pass:**
- Recopilación (Dump) de todos los passwords de conexión dial-up para Internet.

**Ventanas:**
- Lista de todas las ventanas visibles y no visibles desplegadas en el sistema, con opción a cerrar ventana, ocultar ventana, mostrar ventana, deshabilitar y actualizar lista de ventanas.  

**Webcam:**
- Inicializar/Detener la Cámara Web Remota y mostrar capturas múltiples, con la opción de guardar automáticamente en local.

**Pantalla:**
- Capturar la pantalla remota y mostrar capturas múltiples, con la opción de guardar automáticamente en local.

**Registro:**
- Manipular el registro de Windows, con la opción de crear, modificar, borrar cadenas y valores dentro de cualquier Key en la máquina remota.

**Archivos:**
- Navegar dentro de la estructura de archivo de Windows de la máquina remota, poder ejecutar, crear, borrar, subir, descargar archivos remotamente.

**Teclas:**
- Capturar en vivo todas las teclas presionadas en la máquina remota.

**L.A.N:**
- Hacer un broadcast dentro de la red de area local para buscar servidores de NetJoe desplegados y en ejecución.

<center>
<img src="https://github.com/elieser9001/assets/blob/main/netjoe4.png?raw=true"
     alt="netsuite"
     style="width: 400px" />
</center>

<center>
<img src="https://github.com/elieser9001/assets/blob/main/netjoe7.png?raw=true"
     alt="netsuite"
     style="width: 400px" />
</center>

<center>
<img src="https://github.com/elieser9001/assets/blob/main/netjoe6.png?raw=true"
     alt="netsuite"
     style="width: 400px" />
</center>
___

<img src="https://github.com/elieser9001/assets/blob/main/captura_desde_linux_el_exe.png?raw=true"
     alt="cph"
     style="float: left; margin-right: 10px;" />


# C.P.H. CiberPuesto Hack

Este sistema lo desarrollé para poder controlar cualquier computadora remotamente dentro de la red local de un cibercafe que estuviese instalado y funcionando el ciberpuesto 4.0
y también extraer la contraseña de administrador del sistema para poder desbloquear o hacer labores administrativas del ciberpuesto, lo llame C.P.H. (Ciberpuesto Hack)

Lo hice como prueba de concepto de las fallas que me di cuenta de que el Ciberpuesto y Cibercontrol tenian, la primera vez que vi ese sistema funcionando, me di cuenta la similitud que tenía con el sistema que había hecho para mi tesis y me dio curiosidad y en cuanto llegue a mi casa descargue una versión de prueba.

Desensamble el ejecutable y modifique el puerto TCP con el que el Ciberpuesto abría para esperar conexión y entonces hice un pequeño ejecutable que abría el puerto correcto e interceptaba todas las peticiones que venían desde el Cibercontrol (Cliente) y luego se las pasaba al ciberpuesto (un man in the middle) y así pude hacer un log de todos los comandos para poder hacer el sistema C.P.H.

En la parte de la contrasena me fijé que el ciberpuesto en la ruta de c:\windows\system32\ alojaba una base de datos de access la cual estaba bloqueada debido a que el ciberpuesto al iniciar la bloqueaba y no dejaba copiar, por lo que para que me mostrara la contraseña tenía que cerrar en menos de 1 segundo el ciberpuesto enviándole por medio una función de Winapi32 que si mal no recuerdo era ExitProcess pasándole el handle de la ventana, y entonces copiar en una ubicación temporal la base de datos y así extraer y mostrar la contraseña.

**Funciones Remotas**
- Apagar.
- Reniciar.
- Cerrar Sesión.
- Finalizar CiberPuesto (desbloquear computadora).
- Subir / Bajar Volumen.
- Enviar Mensaje y mostrar Mensaje.
- Mostrar la contraseña de administración del CiberPuesto.

Entre los análisis que le hice al Ciberpuesto desensamblando y usando el Windbg para tomar los datos que le enviaba al ciberpuesto me di cuenta de que podía hacer un buffer overflow que desencadenaria una ejecución remota de cualquier payload que hiciese, entonces hice en lenguaje C dos payloads uno para los Windows con service pack 1 y 2 y desde entonces podía tener más control de cualquier computadora del ciber con ciberpuesto 4.0, podía compartir en una carpeta local y entonces ejecutar cualquier ejecutable que colocase en esa carpeta ejecutarlo en la máquina remota, como por ejemplo el ejecutable del servidor del netjoe para hacer más fácil la ejecución remota de órdenes. ( a estos los llamé xcp1.exe para service pack 1 y xcp2.exe para service pack 2)



___

<img src="https://github.com/elieser9001/assets/blob/main/guerrapandilla1.jpg?raw=true"
     alt="cph"
     style="float: left; margin-right: 10px; width: 400px" />

# Script Guerra de Pandillas


Es un script en Python que hice en el 2008 para que jugase guerra de pandillas mientras yo me iba a dormir.

Guerra de pandillas era un juego HTML dentro de Facebook, que simulaba una economía de pandillas por medio de buscar contrincantes y entablar una riña que se podía ganar o no dependiendo varios factores. Con el script que hice analizaba varios factores, entre ellos las propiedades que poseían los posibles contrincantes y entonces por medio del análisis decidir si pelear o no.

El script es del año 2008, cuando estaba comenzando a aprender Python. 😆

```python:
import sys
import httphack
import threading
import sys
import socket
import string
import os
import time

cont_lista_peleas = 0

TIEMPO_REFRESCAR = 30.0
EN_PARA_HACER_MISION = 16
NUM_MISION = 8
MIN_HP = 40 #mi hp minimo para pelear

class c_mi:
  nivel = 0
  puntos = ''
  hp = 0
  hp_max = 0
  sta = 0
  sta_max = 0
  efectivo = 0
  banco = 0

mi = c_mi()

class c_pandillero:
  id = ''
  sig = ''
  nombre = ''
  nivel = 0
  apodo = ''
  esquina = 0
  tienda = 0
  cibercafe = 0
  gimnasio = 0
  bar = 0
  restaurante = 0
  discoteca = 0
  prostibulo = 0
  centro_comercial = 0
  hotel = 0
  casino = 0

cookie_bot = ''

def exit_client():
  raise SystemExit


def extraer(fullstring,strinicio,strfinal):
  _posName = fullstring.find(strinicio)
  
  if (_posName >= 0):
    _posName += len(strinicio)
    _posFinal = fullstring.find(strfinal,_posName)
    _resultado = fullstring[_posName:_posFinal]
  else:
    _resultado = ''
    	
  return _resultado


def dato_nivel(datos):
  resultado = extraer(datos,'"profilebox_item">Nivel: ','</div>')
  
  return resultado

def dato_hp(datos):
  resultado = extraer(datos,'<div>HP: ','</div>')
  
  return resultado


def dato_en(datos):
  resultado = extraer(datos,'<div class="profilebox_item">EN: ','</div>')
  
  return resultado

def dato_en(datos):
  resultado = extraer(datos,'<div class="profilebox_item">EN: ','</div>')
  
  return resultado

def dato_sta(datos):
  resultado = extraer(datos,'<div class="profilebox_item">STA: ','</div>')
  
  return resultado


def dato_banco(datos):
  resultado = extraer(datos,'( Mi cuenta del banco: <span class="green">$','</span>,')
  
  return resultado

def dato_efectivo(datos):
  resultado = extraer(datos,'inero: <span class="green">','</span></div>')
  
  return resultado

def server_paquete(datos):  
  pos_linea = datos.find(chr(13))
  pos_espacio = datos.find(' ')
  
  tipo = datos[0:pos_espacio]

  cgi = extraer(datos,' ',' ')
  servidor = extraer(datos,'Host: ',chr(13))
  cookie = extraer(datos,'Cookie: ',chr(13))

  return ({'tipo':tipo,'cgi':cgi,'servidor':servidor,'cookie':cookie})

  
class letsrock(threading.Thread):
  def run(self):  
    #socket ------------------------------------------------------------------
    sck_servidor = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sck_servidor.bind(('localhost', 8080))
    sck_servidor.listen(5)
    
    conn, addr = sck_servidor.accept()
    sck_servidor.setblocking(0)
        
    _html = ''
  
    puerto = 80

    sck_cliente = socket.socket(socket.AF_INET, socket.SOCK_STREAM)    
    
    while(True):
      _datos_rcv = str(conn.recv(1024))      
    
      if not _datos_rcv:
        break
        conn.close()
      
      
      info_paquete = server_paquete(_datos_rcv)
      
      tipo = info_paquete['tipo']
      servidor = info_paquete['servidor']
      cgi = info_paquete['cgi']
      cookie = info_paquete['cookie']
      
      parametros = ""   
    
      datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']
          
      _html += _datos_rcv
      

def tomar_cookie(conn):
  global cookie_bot
  datos = ''
  
  while(1):
    _datos_rcv = str(conn.recv(1024))
    datos += _datos_rcv
    
    if (len(_datos_rcv) <= 0) or (datos.find("__qcb=")>=0):
      conn.close()
      break
    
  if (len(datos) > 0):
    info_paquete = server_paquete(datos)
        
    tipo = info_paquete['tipo']
    servidor = info_paquete['servidor']
    cgi = info_paquete['cgi']
    cookie = info_paquete['cookie']
    
    if (servidor == 'apps.facebook.com') and (len(cookie) > 0) :
      cookie_bot = cookie

      return True
    else:
      cookie_bot = ''
      print "[-]-Error al inicializar (Intente nuevamente)"
      print datos
      return False
  else:
    return False

def actualizar_datos(datos):
  banco = dato_banco(datos)
  efectivo = dato_efectivo(datos)
  nivel = dato_nivel(datos)
  hp = dato_hp(datos)
  en = dato_en(datos)
  sta = dato_sta(datos)
  
  efectivo = string.replace(efectivo,'$','')
  efectivo = string.replace(efectivo,',','')  
  
  pos_barra_hp = hp.find('/')
  pos_barra_en = en.find('/')
  pos_barra_sta = sta.find('/')  
  pos_barra_nivel = nivel.find(' ')
  
  
  print "EFECTIVO " + efectivo
  print "PRUEBA DE NIVEL: " + nivel[0:pos_barra_nivel]
  print "Puntos: " + extraer(nivel,'(',')')
  print "EN maximo: " + en[pos_barra_en+1:len(en)]
  print "STA: " + sta
  
  
  mi.banco = banco
  mi.efectivo = int(efectivo)
  mi.nivel = int(nivel[0:pos_barra_nivel])
  mi.puntos = extraer(nivel,'(',')')
  mi.hp = int(hp[0:pos_barra_hp])
  mi.en = int(en[0:pos_barra_en])
  mi.en_max = int(en[pos_barra_en+1:len(en)])
  mi.sta = int(sta[0:pos_barra_sta])
  mi.sta_max = int(sta[pos_barra_sta+1:len(sta)])


def ack(cookie_inicial=''):
  global cookie_bot
  try:
    if len(cookie_inicial)>0:    
      cookie = cookie_inicial
      servidor = "apps.facebook.com"
      puerto = 80
      tipo = "POST"
      cgi = "/ajax/chat/buddy_list.php"
      parametros = 'user=702519843&popped_out=false&&force_render=false&buddy_list=1&post_form_id=7f96c82dab148e91ee567685a827f1e7'
      
      paquete = 'POST /ajax/chat/buddy_list.php HTTP/1.1' + chr(13) + chr(10)
      paquete += 'Host: apps.facebook.com' + chr(13) + chr(10)
      paquete += 'User-Agent: Mozilla/5.0 (Windows; U; Windows NT 5.1; es-ES; rv:1.9.0.3) Gecko/2008092417 Firefox/3.0.3' + chr(13) + chr(10)
      paquete += 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8' + chr(13) + chr(10)
      paquete += 'Accept-Language: es-es,es;q=0.8,en-us;q=0.5,en;q=0.3' + chr(13) + chr(10)
      paquete += 'Accept-Encoding: deflate' + chr(13) + chr(10)
      paquete += 'Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7' + chr(13) + chr(10)
      paquete += 'Keep-Alive: 300' + chr(13) + chr(10)
      paquete += 'Proxy-Connection: keep-alive' + chr(13) + chr(10)
      paquete += 'X-SVN-Rev: 130297' + chr(13) + chr(10)
      paquete += 'Content-Type: application/x-www-form-urlencoded; charset=UTF-8' + chr(13) + chr(10)
      paquete += 'Cookie: ' + cookie_inicial + chr(13) + chr(10)      
      paquete += 'Pragma: no-cache' + chr(13) + chr(10)
      paquete += 'Cache-Control: no-cache' + chr(13) + chr(10)
      paquete += 'Content-Length: ' + str(len(parametros)) + chr(13) + chr(10) + chr(13) + chr(10)
      
      paquete += parametros
      
      sck_cliente = socket.socket(socket.AF_INET, socket.SOCK_STREAM)    
      sck_cliente.connect((servidor, puerto))
      sck_cliente.send(paquete)
      
      datos = ''
      
      _datos_rcv = str(sck_cliente.recv(1024))
      datos += _datos_rcv
      
      error_numero = extraer(datos,'"error":',',"')
      
      if error_numero == '0':
        error_info = 'Todo Bien'
        nuevo_xs = extraer(datos,"xs=",';')
        nuevo_time = extraer(datos,'"time":','000,')        
        
        cookie_time = extraer(cookie_bot,"time%22%3A","%2C%22ch")
        cookie_xs = extraer(cookie_bot,"xs=",';')        
        
        if len(nuevo_xs) > 0:
          cookie_bot =  string.replace(cookie_bot,cookie_xs,nuevo_xs)        
        
        if len(cookie_time) > 0:
          cookie_bot = string.replace(cookie_bot,cookie_time,nuevo_time)
      
        tipo = "GET"
        cgi = "/guerra-de-pandillas/bank.php"
        cookie = cookie_bot
        parametros = ""
        
        datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']

        #print datos
        
        if len(datos) > 0:
          actualizar_datos(datos)
          
          print "--------------------------ACK------------------------------------"
          print "    Nivel: " + str(mi.nivel) + " (" + mi.puntos + ")"
          print "       HP: " + str(mi.hp)
          print "       EN: " + str(mi.en)
          print "      STA: " + str(mi.sta)
          print " Efectivo: " + str(mi.efectivo)
          print "    Banco: " + str(mi.banco)
          print ""
          print " Ultima actualizacion: -[" + time.strftime("%H:%M:%S %p - %d/%m/%Y") + "]-"
          print "--------------------------------------------------------------"         
          
          evaluar(cookie)        
      else:
        print "ACK"
        error_info = extraer(datos,'"errorSummary":"','","')
        print "[-]-> Error numero: " + error_numero
        print "[-]-> " + error_info      
    else:
      if len(cookie_bot) > 0 :
        pass
      else:
        print "[-]-Error cookie en blanco"    
  except:
    pass

def doit():
  ack(cookie_bot)
  tmr_ping()
  

def tmr_ping():
	tmrEnv = threading.Timer(TIEMPO_REFRESCAR, doit)
	tmrEnv.start()
	
def hacer_mision(num_mision,cookie):
  servidor = "apps.facebook.com"
  puerto = 80
  tipo = "POST"
  cgi = "/guerra-de-pandillas/job.php"
  parametros = 'fb_sig_locale=es_LA&fb_sig_in_new_facebook=1&fb_sig_time=1227319787.6404&fb_sig_added=1&fb_sig_profile_update_time=1225403288&fb_sig_expires=1227406187&fb_sig_user=702519843&fb_sig_session_key=d358bf8467a0f8f3dbf81c97-702519843&fb_sig_api_key=32d28c1bc20d6febfd2ea928c9f5745e&fb_sig=c53a74e068386e9a1f5766f31387cab5&id=' + str(num_mision) + '&sig=3f867f5ac351d486ce3c117bd10b48a68610dd3c'
  datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']

  #print datos
  
  if len(datos) > 0:
    #gpd = gpdatos(datos)
    actualizar_datos(datos)
    # os.system("cls")
    print "---------------------------Hacermision-----------------------------------"
    print "    Nivel: " + str(mi.nivel)
    print "       HP: " + str(mi.hp)
    print "       EN: " + str(mi.en)
    print "      STA: " + str(mi.sta)
    print " Efectivo: " + str(mi.efectivo)
    print "    Banco: " + str(mi.banco)
    print "--------------------------------------------------------------"
  else:
    print "HACER MISION"
    error_info = extraer(datos,'"errorSummary":"','","')
    print "[-]-> Error numero: " + error_numero
    print "[-]-> " + error_info
    

def depositar(monto,cookie):
  servidor = "apps.facebook.com"
  puerto = 80
  tipo = "POST"
  cgi = "/guerra-de-pandillas/bank.php"
  #cookie = cookie_bot
  parametros = 'fb_sig_locale=es_LA&fb_sig_in_new_facebook=1&fb_sig_time=1226121856.5241&fb_sig_added=1&fb_sig_profile_update_time=1225403288&fb_sig_expires=1226208256&fb_sig_user=702519843&fb_sig_session_key=e43ac5bf49316bec4835d147-702519843&fb_sig_api_key=32d28c1bc20d6febfd2ea928c9f5745e&fb_sig=66c423b3a0380090b688e89ded4a44db&amount=' + str(monto) + '&deposit=Depositar'
  
  datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']  

  #print datos
  
  if len(datos) > 0:
    actualizar_datos(datos)
    # os.system("cls")
    print "--------------------------depositar------------------------------------"
    print "    Nivel: " + str(mi.nivel)
    print "       HP: " + str(mi.hp)
    print "       EN: " + str(mi.en)
    print "      STA: " + str(mi.sta)
    print " Efectivo: " + str(mi.efectivo)
    print "    Banco: " + str(mi.banco)
    print "--------------------------------------------------------------"
  else:
    print "Depositar"
    error_info = extraer(datos,'"errorSummary":"','","')
    print "[-]-> Error numero: " + error_numero
    print "[-]-> " + error_info

    
def evaluar(cookie):
  #$159,900
  #22/22
  
  
  #Nota: Colocar como constante global

  
  while(1):
    if (mi.hp >= MIN_HP):
      resultado = buscar_pelea(cookie)
      #return ({'pandilleros':pandilleros,'parametros_pelea':parametros_pelea})
      pandilleros = resultado['pandilleros']
      parametros_pelea = resultado['parametros_pelea']
      
      for pandillero in pandilleros:
        if (mi.hp >= MIN_HP) and (mi.sta >= 1):
          if ((int(pandillero.nivel) <= mi.nivel) and (pandillero.casino>0) and (pandillero.hotel>0) and (pandillero.estado <> "Grave")):
            print "Elegido " + pandillero.nombre + " para pelear!"
            pelear(pandillero,parametros_pelea,cookie) #QUE ACTUALICE MI HP POR LO MENOS QUE SEA GLOBAL
            print "Pelea con " + pandillero.nombre + " finalizada"
        else:
          break
    else:
      break
  
  int_efectivo = mi.efectivo
  int_en = mi.en
  
  if int_efectivo >= 100:
    depositar(int_efectivo,cookie)
  
  if int_en >= EN_PARA_HACER_MISION:
    hacer_mision(NUM_MISION,cookie)
    
def armar_parametros_pelea(datos):
  resultado = 'fb_sig_locale=es_LA&fb_sig_in_new_facebook=1'
  temp_param = []
  temp_param.append('fb_sig_time')
  temp_param.append('fb_sig_added')
  temp_param.append('fb_sig_profile_update_time')
  temp_param.append('fb_sig_expires')
  temp_param.append('fb_sig_user')
  temp_param.append('fb_sig_session_key')
  temp_param.append('fb_sig_api_key')
  temp_param.append('fb_sig')
  
  for param in temp_param: 
    #temp_param = '&' + param
    resultado += '&' + param + '=' + extraer(datos,'name="' + param + '" value="','" />')
  
  resultado += '&action=fight_single&id=IDPANDILLERO&sig='
  
  #print "EN ARMAR" + resultado
  #exit_client()
  
  return resultado
  
def prueba_data(archivo):
  fileHandle = open (archivo)
  resultado = fileHandle.read()
  fileHandle.close() 
  return resultado

def pedir_lista_peleas(cookie):
  global cont_lista_peleas
  
  servidor = "apps.facebook.com"
  puerto = 80
  tipo = "GET"
  #cgi = '/ajax/ct.php?app_id=19100272286&action_type=3&post_form_id=4621c09af5c8d918cee82aeed4a39ba5&position=3&0.6336457102957316'
  
  #cgi = '/guerra-de-pandillas/fight.php'
  
  if (cont_lista_peleas < 1001):
    cont_lista_peleas += 5
  else:
    cont_lista_peleas = 5
  
  
  cgi = '/guerra-de-pandillas/fight.php?b=' + str(cont_lista_peleas)
  #http://apps.facebook.com/guerra-de-pandillas/fight.php?b=5
  #cookie = cookie_bot
  parametros = ''
  
  datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']

  #print datos  
  
  if len(datos) > 0:    
    return datos
  else:
    print "pedir lista"
    error_numero = extraer(datos,'"error":',',"')
    error_info = extraer(datos,'"errorSummary":"','","')
    print "[-]-> Error numero: " + error_numero
    print "[-]-> " + error_info
    exit_client()

def pelear(pand,parametros_pelea,cookie):
  #print "*********EN PELEAR ID: " + id  
  servidor = "apps.facebook.com"
  puerto = 80
  tipo = "POST"
  cgi = '/guerra-de-pandillas/details.php'
  cookie += '; made_write_conn=1226268812'
  
  parametros = parametros_pelea.replace('IDPANDILLERO',str(pand.id))
  parametros += pand.sig
  
  #print "PARAMETROS DE PELEA: " + parametros
  #exit_client()
  
  datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']
  
  if len(datos) > 0:
    actualizar_datos(datos)
  else:
    print "Error en pelear()"
    error_info = extraer(datos,'"errorSummary":"','","')
    print "[-]-> Error numero: " + error_numero
    print "[-]-> " + error_info
    exit_client()


def buscar_pelea(cookie):
  datos = pedir_lista_peleas(cookie)
  parametros_pelea = armar_parametros_pelea(datos)
  
  #print "PARAMETROS LISTA EN BUSCAR PELEA: " + parametros_lista
  #exit_client()
  
  marcador = '<div class="mod_info">'
  pos_primero = datos.find(marcador)
  
  datos = datos[pos_primero:len(datos)]
  #print datos
  
  marcador2 = '<div class="mod_profile_pic">'
  tmp = datos.split(marcador2) 
  
  pandilleros = []
  
  print "--------------------------Buscando Pelea...------------------------------------"
  print ""
  print ""
  
  #i = 1
  for i in range(5):
    
    dato_pandillero = tmp[i]
    id = extraer(dato_pandillero,'<a name="','"')
    sig = extraer(dato_pandillero,'&#039;,&#039;','&#039;);}')
    nombre = extraer(dato_pandillero,';return true;">','</a><br />')    
    nivel = extraer(dato_pandillero,'Nivel: <span class="green">','</span>')    
    apodo = extraer(dato_pandillero,'Apodo: <span class="blue">','</span>')
    
    if dato_pandillero.find('Estado: <span class="green">') > 0:
      estado = "Normal"
    elif dato_pandillero.find('Estado: <span class="yellow">') > 0:
      estado = "Herido"
    elif dato_pandillero.find('Estado: <span class="red">') > 0:
      estado = "Grave"
    else:
      estado = "Desconocido"
    
    
    pand = c_pandillero()
        
    pand.id = id
    pand.sig = sig
    pand.nombre = nombre
    pand.nivel = int(nivel)
    pand.apodo = apodo
    pand.estado = estado
    
    pand_resultado = propiedades_pandillero(pand,cookie)
    
    #Comentar
    #"""
    print "==================================================="
    print "     ID: " + str(pand_resultado.id)
    print "    SIG: " + str(pand_resultado.sig)
    print " Nombre: " + str(pand_resultado.nombre)
    print "  Nivel: " + str(pand_resultado.nivel)
    print "  Apodo: " + str(pand_resultado.apodo)
    print " Estado: " + str(pand_resultado.estado)    
    print "Esquina: " + str(pand_resultado.esquina)
    print "  Hotel: " + str(pand_resultado.hotel)
    print " Casino: " + str(pand_resultado.casino)
    #print "==================================================="
    #"""
    
    pandilleros.append(pand_resultado)
    
  return ({'pandilleros':pandilleros,'parametros_pelea':parametros_pelea})
  
def desglosar_propiedades_pandillero(datos,pand):  
  marca_esquina = '"blue">Esquina ('  
  marca_tienda = '"blue">Tienda ('
  marca_cibercafe = '"blue">Ciber-caf'
  marca_gimnasio =  '"blue">Gimnasio ('
  marca_bar = '"blue">Bar ('
  marca_restaurante = '"blue">Restaurante ('
  marca_discoteca = '"blue">Discoteca ('
  marca_prostibulo = '"blue">Prost'
  marca_centro_comercial = '"blue">Centro comercial ('
  marca_hotel = '"blue">Hotel ('
  marca_casino = '"blue">Casino ('
  
  
  if datos.find(marca_esquina) > 0:  
    esquina = extraer(datos,marca_esquina,')')
  else:
    esquina = 0
  
  if datos.find(marca_tienda) > 0:  
    tienda = extraer(datos,marca_tienda,')')
  else:
    tienda = 0
    
  if datos.find(marca_cibercafe) > 0:  
    cibercafe = extraer(datos,marca_cibercafe,'</span>')
    cibercafe = extraer(cibercafe,'(',')')
  else:
    cibercafe = 0
  
  if datos.find(marca_gimnasio) > 0:  
    gimnasio =  extraer(datos,marca_gimnasio,')')
  else:
    gimnasio = 0
  
  if datos.find(marca_bar) > 0:  
    bar = extraer(datos,marca_bar,')')
  else:
    bar = 0
  
  if datos.find(marca_restaurante) > 0:  
    restaurante = extraer(datos,marca_restaurante,')')
  else:
    restaurante = 0
  
  if datos.find(marca_discoteca) > 0:  
    discoteca = extraer(datos,marca_discoteca,')')
  else:
    discoteca = 0
  
  if datos.find(marca_prostibulo) > 0:  
    prostibulo = extraer(datos,marca_prostibulo,'</span>')
    prostibulo = extraer(prostibulo,'(',')')
  else:
    prostibulo = 0
  
  if datos.find(marca_centro_comercial) > 0:  
    centro_comercial = extraer(datos,marca_centro_comercial,')')
  else:
    centro_comercial = 0
  
  if datos.find(marca_hotel) > 0:  
    hotel = extraer(datos,marca_hotel,')')
  else:
    hotel = 0
  
  if datos.find(marca_casino) > 0:  
    casino = extraer(datos,marca_casino,')')
  else:
    casino = 0
  
  pand.esquina = esquina
  pand.tienda = tienda
  pand.cibercafe = cibercafe
  pand.gimnasio = gimnasio
  pand.bar = bar
  pand.restaurante = restaurante
  pand.discoteca = discoteca
  pand.prostibulo = prostibulo
  pand.centro_comercial = centro_comercial
  pand.hotel = hotel
  pand.casino = casino
  
  return pand

def propiedades_pandillero(pand,cookie):
  id_pandillero = pand.id
  
  servidor = "apps.facebook.com"
  puerto = 80
  tipo = "GET"
  cgi = "/guerra-de-pandillas/details.php?id=" + id_pandillero
  #cookie = cookie_bot
  parametros = ''
  
  datos = httphack.peticionhttp(servidor,cgi,tipo,parametros,cookie=cookie,debug_mode=True,encode_cgi=False)['data']

  #print datos
  
  if len(datos) > 0:    
    pand_resultado = desglosar_propiedades_pandillero(datos,pand)
  else:
    print "Propiedades Pandillero"
    error_info = extraer(datos,'"errorSummary":"','","')
    print "[-]-> Error numero: " + error_numero
    print "[-]-> " + error_info   
    exit_client()
  
  return pand_resultado

def main():
  global cookie_bot
  
  os.system("cls")
  
  sck_servidor = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  
  sck_servidor.bind((socket.gethostname(), 8080))
  
  
  sck_servidor.listen(5)

  while (1):
    conn, addr = sck_servidor.accept()  
    if tomar_cookie(conn) == True:
      sck_servidor.close()
      break
  
  ack(cookie_bot)
  tmr_ping()

if __name__ == '__main__':
  main()





You can use the [editor on GitHub](https://github.com/elieser9001/log/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/elieser9001/log/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
