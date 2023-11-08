
using System;
using System.Collections.Generic;
namespace DeepSpace
{

	class Estrategia
	{
		
		
		public String Consulta1( ArbolGeneral<Planeta> arbol)
		{
			
			return EsBot(arbol).getDatoRaiz().Poblacion().ToString();
			return "Esta a " + BuscarbotRecusivo(arbol).ToString() + " Planetas de la raiz" ;
		}


		public String Consulta2( ArbolGeneral<Planeta> arbol)
		{
			return "Los planetas detras del bot son: "+ PlanetasDetras(EsBot(arbol));;
		}


		public String Consulta3( ArbolGeneral<Planeta> arbol)
		{	
			int totalArbol= arbol.getDatoRaiz().Poblacion()+TotaldePlanetasNivel2(arbol)+TotaldePlanetasNivel3(arbol)+TotaldePlanetasNivel4(arbol);
			int Porcentaje1=(100*arbol.getDatoRaiz().Poblacion())/totalArbol;
			int Porcentaje2= (100*TotaldePlanetasNivel2(arbol))/totalArbol;
			int Porcentaje3= (100*TotaldePlanetasNivel3(arbol))/totalArbol;
			int Porcentaje4= (100*TotaldePlanetasNivel4(arbol))/totalArbol;
			
			string nivel1=Porcentaje1.ToString();
			string nivel2= Porcentaje2.ToString();
			string nivel3=Porcentaje3.ToString();
			string nivel4=Porcentaje4.ToString();
			
		return "Total: "+totalArbol +"Porcentaje(n1): "+nivel1+"% "+"Porcentaje(n2): "+nivel2+"% "+"Porcentaje(n3): "+nivel3+" % "+"Porcentaje(n4): "+nivel4+"%" ;
		}
		
	public Movimiento CalcularMovimiento(ArbolGeneral<Planeta> arbol)
		{ 	
			
			Planeta bot = EsBot(arbol).getDatoRaiz();
			Planeta raizBot= BuscaRaizBot(arbol).getDatoRaiz();
			Planeta jugador= EsJugador(arbol).getDatoRaiz();
			Planeta raizJugador= BuscaRaizJugador(arbol).getDatoRaiz();
			
			
			if(raizBot == jugador){
						Movimiento ataqueJugador=new Movimiento(bot,raizBot);
					return ataqueJugador;}
			if (raizBot == raizJugador && raizBot.EsPlanetaDeLaIA() != true){
				Movimiento ataqueJugador=new Movimiento(bot,raizBot);
				return ataqueJugador;
			}
			else{
				foreach(var hijo in EsBot(arbol).getHijos()){
					if( hijo.getDatoRaiz() == jugador){
						Movimiento ataqueJugador=new Movimiento(bot,hijo.getDatoRaiz());
					return ataqueJugador;}
					if (hijo.getDatoRaiz() == raizJugador && hijo.getDatoRaiz().EsPlanetaDeLaIA() !=true){
				Movimiento ataqueJugador=new Movimiento(bot,hijo.getDatoRaiz());
				return ataqueJugador;}
				
				else{
						foreach(var hijo1 in hijo.getHijos()){
						if( hijo1.getDatoRaiz() == jugador){
						Movimiento ataqueJugador=new Movimiento(bot,hijo1.getDatoRaiz());
							return ataqueJugador;}
							if (hijo1.getDatoRaiz() == raizJugador && hijo1.getDatoRaiz().EsPlanetaDeLaIA() !=true){
							Movimiento ataqueJugador=new Movimiento(bot,hijo1.getDatoRaiz());
							return ataqueJugador;}
						
							else{
								foreach(var hijo2 in hijo1.getHijos()){
									if( hijo2.getDatoRaiz() == jugador){
									Movimiento ataqueJugador=new Movimiento(bot,hijo2.getDatoRaiz());
										return ataqueJugador;}
									if (hijo2.getDatoRaiz() == raizJugador && hijo2.getDatoRaiz().EsPlanetaDeLaIA() !=true){
										Movimiento ataqueJugador=new Movimiento(bot,hijo2.getDatoRaiz());
										return ataqueJugador;}
									else{
										foreach(var hijo3 in hijo2.getHijos()){
											if( hijo3.getDatoRaiz() == jugador){
												Movimiento ataqueJugador=new Movimiento(bot,hijo3.getDatoRaiz());
													return ataqueJugador;}
											if (hijo3.getDatoRaiz() == raizJugador && hijo3.getDatoRaiz().EsPlanetaDeLaIA() !=true){
												Movimiento ataqueJugador=new Movimiento(bot,hijo3.getDatoRaiz());
												return ataqueJugador;}
						}
				
				
				}
									
									
						}
				
				
				}
						}
				
				
				}
				
				
				
				
				}
			
			
			
			}
			
			Movimiento ataqueFalso= new Movimiento(bot,raizBot);
			return ataqueFalso;}
	
	public ArbolGeneral<Planeta> BuscaBots(ArbolGeneral<Planeta> arbol){
		
			Planeta a= arbol.getDatoRaiz();
			if (a.EsPlanetaDeLaIA() == true){return arbol;}
			else {
				foreach(var hijo in arbol.getHijos()){
					a=hijo.getDatoRaiz();
					if (a.EsPlanetaDeLaIA() == true){return hijo;}
					else{
						foreach(var hijo1 in hijo.getHijos()){
							a=hijo1.getDatoRaiz();
							if (a.EsPlanetaDeLaIA() == true){return hijo1;}
							else{
								foreach(var hijo2 in hijo1.getHijos()){
									a=hijo2.getDatoRaiz();
									if (a.EsPlanetaDeLaIA() == true){return hijo2;}
								}
						}
					}
				}
			}
			return arbol;
			}}
	
	public int PlanetasDetras(ArbolGeneral<Planeta> arbol){
		Cola<Planeta> lista=new Cola<Planeta>();
		foreach(var hijo in arbol.getHijos()){
			lista.encolar(hijo.getDatoRaiz());
			foreach(var hijo1 in hijo.getHijos()){
				lista.encolar(hijo1.getDatoRaiz());
				foreach(var hijo2 in hijo1.getHijos()){
					lista.encolar(hijo2.getDatoRaiz());}
			}
		}
		return lista.Contar();
	}
	
	public ArbolGeneral<Planeta> BuscaRaizBot(ArbolGeneral<Planeta> arbol){
			foreach(var hijo in arbol.getHijos()){
				if (hijo == EsBot(hijo)){return arbol;}
				else{
					foreach(var hijo1 in hijo.getHijos())
						if(hijo1== EsBot(hijo1)){return hijo;}
					else{
						foreach(var hijo2 in hijo1.getHijos()){
							if(hijo2 ==EsBot(hijo2)){return hijo1;}
						
						}	
					}
				}
			}
		
	return arbol;
	}
	
	
	
	
	
	
	
	
	public int BuscarbotRecusivo(ArbolGeneral<Planeta> arbol){
			
			Planeta a= arbol.getDatoRaiz();
			
			if (a.EsPlanetaDeLaIA()== true){return 0 ;} // Esta en la Raiz
			
			else{
			
				foreach(var hijo in arbol.getHijos()){
					
					a=hijo.getDatoRaiz();
					if (a.EsPlanetaDeLaIA()== true){return 1;}
					else {
						foreach(var hijos1 in hijo.getHijos()){
							a=hijos1.getDatoRaiz();
							if(a.EsPlanetaDeLaIA()==true){return 2;}
							foreach(var hijos2 in hijos1.getHijos()){
								a=hijos2.getDatoRaiz();
								if(a.EsPlanetaDeLaIA()==true){return 3;}
								}
						}
					}
			}
			}
			return 0;
		}
	



	public ArbolGeneral<Planeta> EsBot(ArbolGeneral<Planeta>arbol){
		Planeta PlanetDondeEstoy= arbol.getDatoRaiz();
		if (PlanetDondeEstoy.EsPlanetaDeLaIA()==true){
		return arbol;
		}
		if(arbol.esHoja()==true){
		return null;
		}
		else{
			foreach(var hijo in arbol.getHijos()){
			ArbolGeneral<Planeta> resultado = EsBot(hijo);
			if (resultado!= null){
			return resultado;
			}
		}}
		return null;
	}

	public ArbolGeneral<Planeta> EsJugador(ArbolGeneral<Planeta>arbol){
		Planeta PlanetDondeEstoy= arbol.getDatoRaiz();
		if (PlanetDondeEstoy.EsPlanetaDelJugador()==true){
		return arbol;
		}
		if(arbol.esHoja()==true){
		return null;
		}
		else{
			foreach(var hijo in arbol.getHijos()){
			ArbolGeneral<Planeta> resultado = EsJugador(hijo);
			if (resultado!= null){
			return resultado;
			}
		}}
		return null;
	}
	
	
	
	
	
	
	public ArbolGeneral<Planeta> BuscaRaizJugador(ArbolGeneral<Planeta> arbol){
			foreach(var hijo in arbol.getHijos()){
				if (hijo == EsJugador(hijo)){return arbol;}
				else{
					foreach(var hijo1 in hijo.getHijos())
						if(hijo1== EsJugador(hijo1)){return hijo;}
					else{
						foreach(var hijo2 in hijo1.getHijos()){
							if(hijo2 ==EsJugador(hijo2)){return hijo1;}
						
						}	
					}
				}
			}
		
	return arbol;
	}
	
	
	
	
	
	
	
	public int TotaldePlanetasNivel2(ArbolGeneral<Planeta>Arbol){
		int total=0;
		foreach(var hijos in Arbol.getHijos()){
			total=hijos.getDatoRaiz().Poblacion()+total;
		}
		return total;
	}
	
	public int TotaldePlanetasNivel3(ArbolGeneral<Planeta>arbol){
		int total=0;
		foreach(var hijos in arbol.getHijos()){
			foreach(var hijo1 in hijos.getHijos()){
			        	total=hijo1.getDatoRaiz().Poblacion()+total;}
		}
	return total;
	}
	
	public int TotaldePlanetasNivel4(ArbolGeneral<Planeta> arbol){
	
	int total=0;
		
		foreach(var hijos in arbol.getHijos()){
			foreach(var hijo1 in hijos.getHijos()){
			foreach(var hijo2 in hijo1.getHijos()){
			        	total=hijo2.getDatoRaiz().Poblacion()+total;}
		}}
	
	return total;
	}
		}
	}
