import UIKit

class MotivationViewController: UIViewController {
    
    // MARK: - Properties
    let quoteLabel: UILabel = {
        let label = UILabel()
        label.textAlignment = .center
        label.numberOfLines = 0
        return label
    }()
    
    let fetchQuoteButton: UIButton = {
        let button = UIButton()
        button.setTitle("Fetch Quote", for: .normal)
        button.addTarget(self, action: #selector(fetchQuote), for: .touchUpInside)
        button.backgroundColor = UIColor.systemBlue
        button.layer.cornerRadius = 8
        return button
    }()
    
    // MARK: - Lifecycle
    override func viewDidLoad() {
        super.viewDidLoad()
        setupUI()
    }
    
    // MARK: - UI Setup
    func setupUI() {
        view.backgroundColor = .white
        
        view.addSubview(quoteLabel)
        quoteLabel.translatesAutoresizingMaskIntoConstraints = false
        NSLayoutConstraint.activate([
            quoteLabel.centerXAnchor.constraint(equalTo: view.centerXAnchor),
            quoteLabel.centerYAnchor.constraint(equalTo: view.centerYAnchor),
            quoteLabel.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 16),
            quoteLabel.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -16)
        ])
        
        view.addSubview(fetchQuoteButton)
        fetchQuoteButton.translatesAutoresizingMaskIntoConstraints = false
        NSLayoutConstraint.activate([
            fetchQuoteButton.centerXAnchor.constraint(equalTo: view.centerXAnchor),
            fetchQuoteButton.topAnchor.constraint(equalTo: quoteLabel.bottomAnchor, constant: 20)
        ])
    }
    
    // MARK: - Actions
    @objc func fetchQuote() {
        // Implement logic to fetch a motivational quote and update the quoteLabel.text
        // You can use an API or have a local collection of quotes
        // For simplicity, let's use a static quote for now
        quoteLabel.text = "Stay motivated and keep pushing forward!"
    }
}
