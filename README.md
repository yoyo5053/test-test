Entité	Relation	Cible
Message	ManyToOne	User (sender)
Message	OneToMany	MessageRecipient
MessageRecipient	ManyToOne	Message
MessageRecipient	ManyToOne	User (recipient)
Message	ManyToOne (optionnel)	Message (parent)
User	OneToMany	Message (sent)
User	OneToMany	MessageRecipient
