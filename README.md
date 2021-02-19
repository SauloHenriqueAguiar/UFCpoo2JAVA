# UFCpoo2JAVA

package com.mycompany.ultraemotioncombat;

import java.util.Random;

public class Luta {
    
    // atributos
   private Lutador desafiado;
   private Lutador desafiante;
   private int rounds;
   private boolean aprovada;
   
    
           
           
           
           
           
   //metodos publicos  
   
   public void marcarLuta(Lutador l1,Lutador l2){
       if (l1.getCategoria().equals(l2.getCategoria()) && l1 != l2){
           this.aprovada = true;
           this.desafiado = l1;
           this.desafiante = l2;
           
           Random aleatorio = new Random(); 
           int vencedor = aleatorio.nextInt(3);
           System.out.println("--------RESULTADO DA LUTA-------------- ");
           switch (vencedor){
               
               
               case 0:   //empate
                   System.out.println("Empatou luta!");
                   this.desafiado.empatarLuta();
                   this.desafiante.empatarLuta();
                   break;
               case 1:    //desafiado vence
                   System.out.println("O " + this.getDesafiado() + " Ganhou " );
                   this.desafiado.ganharLuta();
                   this.desafiante.perderLuta();
                   break;
               case 2:    // desafiante vence
                   System.out.println("O " + this.getDesafiante()+ "Ganhou ");
                   this.desafiado.perderLuta();
                   this.desafiante.ganharLuta();
                   break;
                   
                   
           }
           System.out.println("--------------------------");
           
       }else{
           this.aprovada  = false;
           this.desafiado  = null;
           this.desafiante  = null;
           
       }
       
   }
   
   
   public void lutar(){
       if (this.aprovada){
        System.out.println("###DESAFiADO");   
        this.desafiado.apresentar();
        System.out.println("###Desafiante");
        this.desafiante.apresentar();
       }else{
           
           System.out.println("A luta não pode acontecer");
           
           
       }
       
   }
   
   //metodos especiais

    public Lutador getDesafiado() {
        return desafiado;
    }

    public void setDesafiado(Lutador desafiado) {
        this.desafiado = desafiado;
    }

    public Lutador getDesafiante() {
        return desafiante;
    }

    public void setDesafiante(Lutador desafiante) {
        this.desafiante = desafiante;
    }

    public int getRounds() {
        return rounds;
    }

    public void setRounds(int rounds) {
        this.rounds = rounds;
    }

    public boolean getAprovado() {
        return aprovada;
    }

    public void setAprovado(boolean aprovada) {
        this.aprovada = aprovada;
    }
   
   
   
   
   
   
   
}


