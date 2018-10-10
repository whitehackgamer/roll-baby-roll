# roll-baby-roll
roll baby roll

import UIKit

class ViewController: UIViewController {

    var randomDiceIndex3 : Int = 0
    var randomDiceIndex1 : Int = 0
    
    let diceArray = ["dice1","dice2","dice3","dice4","dice5","dice6"]
    
    @IBOutlet weak var diceImageView3: UIImageView!
    @IBOutlet weak var diceImageView1: UIImageView!
    
    override func viewDidLoad() {
        super.viewDidLoad()
      
        updatedDiceImages()
        
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    @IBAction func playButtonPressed(_ sender: UIButton) {
        
        updatedDiceImages()
        
    }
    
    func updatedDiceImages(){
        randomDiceIndex3 = Int(arc4random_uniform(6))
        randomDiceIndex1 = Int(arc4random_uniform(6))
        
        diceImageView3.image = UIImage(named: diceArray[randomDiceIndex3])
        diceImageView1.image = UIImage(named: diceArray[randomDiceIndex1])
    }
    
    override func motionEnded(_ motion: UIEventSubtype, with event: UIEvent?) {
        
        updatedDiceImages()
    }
    
    
}

